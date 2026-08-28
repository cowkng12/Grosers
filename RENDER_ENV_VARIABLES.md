# 🔑 Environment Variables для Render

## Скопируй и вставь эти переменные в Render Dashboard → Environment

### 1. NODE_ENV
```
production
```

### 2. TELEGRAM_BOT_TOKEN ⚠️ ВАЖНО!
```
8943651691:AAHxXhPySHhwOcQweTxf8_uLRpkMQa5KQBw
```

### 3. TELEGRAM_BOT_USERNAME
```
@GrozersStore_bot
```

### 4. ADMIN_CHAT_ID
```
8781709394
```

### 5. WEB_APP_URL
```
https://grozersstore-miniapp.onrender.com
```

### 6. ACTIVATION_SITE_URL
```
https://grozersstore-miniapp.onrender.com/activate
```

```
@GrozersStore
```

```
https://t.me/GrozersStore
```

### 9. SKIP_CHANNEL_CHECK ⚠️ ВАЖНО для работы без канала!
```
true
```

### 10. SELLER_URL
```
https://t.me/metifrysell
```

### 11. CRYPTO_PAY_API_URL
```
https://pay.crypt.bot/api
```

### 12. CRYPTO_PAY_ASSET
```
USDT
```

### 13. SUPABASE_STORE_KEY
```
grozersstore
```

### 14. ACCOUNT_DELIVERY_THRESHOLD
```
1
```

### 15. TON_USD_RATE
```
1.31
```

### 16. WALLET_PAY_TON_ADDRESS
```
UQC8r4dra0Gy1VlxktwRnsTRTcPoKNoqK4xQH94P3SuRRYWC
```

### 17. WALLET_PAY_TRC20_ADDRESS
```
TJDqXkQx5nqFhq7RNtySUMCYTZ5Hk96o3G
```

---

## 📋 Как добавить в Render:

1. Открой https://dashboard.render.com/web/srv-da7gpmajnfac738c0nmg
2. Слева меню → **Environment**
3. Для каждой переменной:
   - Нажми **+ Add Environment Variable**
   - KEY: скопируй название (например: `NODE_ENV`)
   - VALUE: скопируй значение (например: `production`)
   - Нажми **Save**

4. После добавления всех переменных нажми **"Save Changes"** внизу страницы
5. Render автоматически перезапустит сервис

---

## ⚠️ САМЫЕ ВАЖНЫЕ переменные:

1. **TELEGRAM_BOT_TOKEN** - без него бот не запустится
2. **SKIP_CHANNEL_CHECK** = `true` - без этого будет требовать подписку на канал
3. **WEB_APP_URL** - адрес приложения
4. **ADMIN_CHAT_ID** - твой Telegram ID для админ команд

---

## 🔄 Альтернатива - массовый импорт

Если в Render есть кнопка **Import from .env**, используй этот формат:

```env
NODE_ENV=production
TELEGRAM_BOT_TOKEN=8943651691:AAHxXhPySHhwOcQweTxf8_uLRpkMQa5KQBw
TELEGRAM_BOT_USERNAME=@GrozersStore_bot
ADMIN_CHAT_ID=8781709394
WEB_APP_URL=https://grozersstore-miniapp.onrender.com
ACTIVATION_SITE_URL=https://grozersstore-miniapp.onrender.com/activate
SKIP_CHANNEL_CHECK=true
SELLER_URL=https://t.me/metifrysell
CRYPTO_PAY_API_URL=https://pay.crypt.bot/api
CRYPTO_PAY_ASSET=USDT
SUPABASE_STORE_KEY=grozersstore
ACCOUNT_DELIVERY_THRESHOLD=1
TON_USD_RATE=1.31
WALLET_PAY_TON_ADDRESS=UQC8r4dra0Gy1VlxktwRnsTRTcPoKNoqK4xQH94P3SuRRYWC
WALLET_PAY_TRC20_ADDRESS=TJDqXkQx5nqFhq7RNtySUMCYTZ5Hk96o3G
```

Скопируй весь блок выше и импортируй через Render UI.
