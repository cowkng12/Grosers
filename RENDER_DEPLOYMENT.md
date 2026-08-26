# 🚀 Инструкция по деплою на Render

## Быстрый старт

### Вариант 1: Через Blueprint (рекомендуется)

1. Зайдите на [Render Dashboard](https://dashboard.render.com/)
2. Нажмите **"New"** → **"Blueprint"**
3. Подключите GitHub репозиторий: `https://github.com/cowkng12/Grosers`
4. Render автоматически обнаружит `render.yaml` и создаст сервис
5. Заполните секретные переменные (см. ниже)
6. Нажмите **"Apply"**

### Вариант 2: Вручную

1. Зайдите на [Render Dashboard](https://dashboard.render.com/)
2. Нажмите **"New"** → **"Web Service"**
3. Подключите репозиторий `cowkng12/Grosers`
4. Настройки:
   - **Name:** `grozersstore-miniapp`
   - **Environment:** `Node`
   - **Build Command:** `npm install && npm run build`
   - **Start Command:** `npm start`
   - **Plan:** `Free` (или выберите платный)
5. Добавьте переменные окружения (см. ниже)
6. Нажмите **"Create Web Service"**

---

## 🔐 Обязательные переменные окружения

Эти переменные нужно заполнить в Render Dashboard → Environment:

### Telegram Bot
```
TELEGRAM_BOT_TOKEN=<ваш_токен_от_BotFather>
ADMIN_CHAT_ID=<ваш_telegram_id>
```

### URL приложения
```
WEB_APP_URL=https://grozersstore-miniapp.onrender.com
ACTIVATION_SITE_URL=https://grozersstore-miniapp.onrender.com/activate
```

### Контакты
```
SELLER_URL=https://t.me/metifrysell
SUPPORT_BOT_URL=https://t.me/your_support_bot
```

### Платежи (опционально)
```
CRYPTO_PAY_TOKEN=<токен_от_CryptoBot>
```

### Supabase (рекомендуется для production)
```
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_ROLE_KEY=<ваш_service_role_key>
```

---

## 📝 Переменные уже настроенные в render.yaml

Эти значения уже есть в `render.yaml` и их можно не менять:

- `NODE_ENV=production`
- `TELEGRAM_BOT_USERNAME=@GrozersStore_bot`
- `REQUIRED_CHANNEL_USERNAME=@GrozersStore`
- `REQUIRED_CHANNEL_URL=https://t.me/GrozersStore`
- `CRYPTO_PAY_API_URL=https://pay.crypt.bot/api`
- `CRYPTO_PAY_ASSET=USDT`
- `TON_USD_RATE=1.31`
- `WALLET_PAY_TON_ADDRESS=...`
- `WALLET_PAY_TRC20_ADDRESS=...`
- `SUPABASE_STORE_KEY=grozersstore`
- `ACCOUNT_DELIVERY_THRESHOLD=0.1`

---

## 🗄️ Настройка Supabase (рекомендуется)

Без Supabase данные будут храниться во временном файле на Render и пропадут после перезапуска.

### 1. Создайте проект на supabase.com

### 2. Выполните SQL в SQL Editor:

```sql
create table if not exists app_store (
  key text primary key,
  data jsonb not null default '{}'::jsonb,
  updated_at timestamptz not null default now()
);
```

### 3. Получите credentials:

- **Project Settings** → **API**
- Скопируйте `Project URL` → `SUPABASE_URL`
- Скопируйте `service_role key` → `SUPABASE_SERVICE_ROLE_KEY`

### 4. Добавьте в Render Environment

---

## 🤖 Настройка Telegram бота

### 1. Создайте бота через @BotFather:

```
/newbot
Название: GrozersStore
Username: GrozersStore_bot
```

### 2. Получите токен и добавьте в `TELEGRAM_BOT_TOKEN`

### 3. Настройте Web App кнопку (после деплоя):

```
/setmenubutton
@GrozersStore_bot
Текст кнопки: Open
URL: https://grozersstore-miniapp.onrender.com
```

### 4. Получите ваш ADMIN_CHAT_ID:

- Напишите `/myid` боту после запуска
- Или используйте @userinfobot

---

## ✅ Проверка деплоя

После успешного деплоя:

1. **Health Check:** https://grozersstore-miniapp.onrender.com/health
   - Должен вернуть: `{"ok":true,"service":"grozersstore-miniapp"}`

2. **Frontend:** https://grozersstore-miniapp.onrender.com
   - Должен открыться каталог товаров

3. **Activation Page:** https://grozersstore-miniapp.onrender.com/activate
   - Страница активации ключей

4. **Telegram Bot:** Откройте `@GrozersStore_bot` и нажмите `/start`

---

## 🔧 Обновление кода

После изменений в GitHub:

1. **Auto Deploy включен** в `render.yaml` → Render автоматически задеплоит изменения
2. Или вручную: Render Dashboard → Service → **"Manual Deploy"** → **"Deploy latest commit"**

---

## 📊 Мониторинг

- **Logs:** Render Dashboard → Service → **Logs**
- **Metrics:** Render Dashboard → Service → **Metrics**
- **Health Checks:** автоматически каждые 5 минут на `/health`

---

## 🆘 Troubleshooting

### Ошибка: "Bot token is invalid"
- Проверьте `TELEGRAM_BOT_TOKEN` в Environment
- Токен должен быть без пробелов и переносов строк

### Ошибка: "Supabase store load failed"
- Проверьте `SUPABASE_URL` и `SUPABASE_SERVICE_ROLE_KEY`
- Убедитесь, что таблица `app_store` создана

### Бот не отвечает
- Проверьте, что сервис запущен в Render
- Проверьте логи: могут быть ошибки подключения к Telegram API

### Frontend не загружается
- Проверьте, что `npm run build` выполнился успешно в логах
- Проверьте, что папка `dist` создана

---

## 💰 Стоимость

- **Free Plan:** Засыпает после 15 минут неактивности, 750 часов/месяц
- **Starter Plan ($7/мес):** Всегда активен, без лимитов
- **Standard/Pro:** Для высоких нагрузок

---

## 📞 Поддержка

- [Render Docs](https://render.com/docs)
- [Render Community](https://community.render.com/)
- [GitHub Issues](https://github.com/cowkng12/Grosers/issues)
