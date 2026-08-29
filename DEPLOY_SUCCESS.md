# ✅ RENDER ДЕПЛОЙ ЗАВЕРШЁН!

## 🎉 Статус: LIVE

**URL приложения:** https://grozersstore-miniapp.onrender.com
**Dashboard:** https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg
**Service ID:** srv-da7gpmajnfac738c0nmg

---

## ✅ Что настроено

### 1. Сервис создан
- ✅ Name: `grozersstore-miniapp`
- ✅ Region: Oregon
- ✅ Plan: Free
- ✅ Auto-deploy: Enabled (деплой при push в main)
- ✅ Build: `npm install --include=dev && npm run build`
- ✅ Start: `npm start`
- ✅ Health Check: `/health`

### 2. Environment Variables
✅ **NODE_ENV** = production
✅ **TELEGRAM_BOT_TOKEN** = 8943651691:AAHxXhPySHhwOcQweTxf8_uLRpkMQa5KQBw
✅ **TELEGRAM_BOT_USERNAME** = @GrozersStore_bot
✅ **ADMIN_CHAT_ID** = 8781709394
✅ **WEB_APP_URL** = https://grozersstore-miniapp.onrender.com
✅ **ACTIVATION_SITE_URL** = https://grozersstore-miniapp.onrender.com/activate
✅ **SELLER_URL** = https://t.me/metifrysell
✅ **CRYPTO_PAY_API_URL** = https://pay.crypt.bot/api
✅ **CRYPTO_PAY_ASSET** = USDT
✅ **SUPABASE_STORE_KEY** = grozersstore
✅ **ACCOUNT_DELIVERY_THRESHOLD** = 1
✅ **WALLET_PAY_TON_ADDRESS** = UQC8r4dra0Gy1VlxktwRnsTRTcPoKNoqK4xQH94P3SuRRYWC
✅ **WALLET_PAY_TRC20_ADDRESS** = TJDqXkQx5nqFhq7RNtySUMCYTZ5Hk96o3G

### 3. GitHub Integration
✅ Репозиторий подключен: https://github.com/cowkng12/Grosers
✅ Auto-deploy при push в main branch
✅ Последний commit задеплоен

---

## 🔗 Ссылки для проверки

Проверь эти URL в браузере:

1. **Health Check:** https://grozersstore-miniapp.onrender.com/health
   - Должен показать: `{"ok":true,"service":"grozersstore-miniapp"}`

2. **Frontend (Каталог):** https://grozersstore-miniapp.onrender.com
   - Должен открыться каталог с AI-подписками

3. **Активация:** https://grozersstore-miniapp.onrender.com/activate
   - Страница для активации ключей

4. **Telegram Bot:** https://t.me/GrozersStore_bot
   - Нажми `/start` - должно открыться меню

---

## ⚠️ Что нужно сделать дополнительно

### 1. Настроить Web App кнопку в боте
Отправь @BotFather:
```
/setmenubutton
@GrozersStore_bot
```
Затем:
- **Текст кнопки:** Open
- **URL:** https://grozersstore-miniapp.onrender.com

### 2. Добавить второго админа (опционально)
Если хочешь добавить второго админа (ID: 8377620976), нужно:
- Зайти в Render Dashboard → Environment
- Изменить `ADMIN_CHAT_ID` на: `8781709394,8377620976`
- Или настроить проверку в коде для нескольких админов

### 3. Настроить CryptoBot (когда будет токен)
Когда получишь токен от CryptoBot:
- Добавить в Render Environment: `CRYPTO_PAY_TOKEN=<токен>`
- Сервис автоматически перезапустится

### 4. Настроить Supabase (рекомендуется для production)
Без Supabase данные хранятся во временном файле и теряются при рестарте.

**Быстрая настройка:**
1. Создай проект на https://supabase.com
2. SQL Editor → выполни:
```sql
create table if not exists app_store (
  key text primary key,
  data jsonb not null default '{}'::jsonb,
  updated_at timestamptz not null default now()
);
```
3. Project Settings → API → скопируй:
   - `Project URL` → `SUPABASE_URL`
   - `service_role key` → `SUPABASE_SERVICE_ROLE_KEY`
4. Добавь в Render Environment

---

## 📊 Мониторинг

- **Logs:** https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg/logs
- **Metrics:** https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg/metrics
- **Events:** https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg/events

---

## 🔄 Обновление кода

При push в GitHub main branch автоматически запустится деплой:
```bash
git add .
git commit -m "Update"
git push
```

Или вручную в Dashboard: **Manual Deploy** → **Deploy latest commit**

---

## 💰 Free Plan лимиты

- ⏰ Засыпает после 15 минут неактивности
- 🔄 Холодный старт ~30 секунд
- 📊 750 часов/месяц бесплатно
- 💾 Без persistent storage (используй Supabase!)

Для всегда-активного сервиса → Upgrade to Starter ($7/мес)

---

## ✅ Чек-лист первого запуска

- [ ] Открыть https://grozersstore-miniapp.onrender.com
- [ ] Проверить /health endpoint
- [ ] Открыть @GrozersStore_bot
- [ ] Нажать /start в боте
- [ ] Проверить, что меню открывается
- [ ] Настроить Web App кнопку через @BotFather
- [ ] Подписаться на канал @GrozersStore (если есть)
- [ ] Протестировать пополнение баланса (когда будет CryptoBot токен)
- [ ] Настроить Supabase для сохранения данных

---

## 🆘 Если что-то не работает

1. **Проверь логи:** https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg/logs
2. **Проверь env переменные:** Dashboard → Environment
3. **Перезапусти сервис:** Dashboard → Manual Deploy → Clear build cache & deploy
4. **Проверь health:** https://grozersstore-miniapp.onrender.com/health

---

Всё готово! 🎉 Бот должен работать!
