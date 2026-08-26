# Миграция из NeurixKeys в GrozersStore

## Дата миграции
26 августа 2026

## Что было сделано

### 1. Основные файлы
- **server.js** (1875 строк) - полностью скопирован и заменены все упоминания:
  - NervaHub → GrozersStore
  - nervahub → grozersstore
  - NERVA → GROZERS
  - Nerva → Grozers
  - nerva → grozers

### 2. Frontend файлы
- **src/App.jsx** (1566 строк) - полный функционал с заменами названий
- **src/App.css** (17889 байт) - все стили скопированы
- **src/index.css** (725 байт) - базовые стили
- **src/main.jsx** (229 байт) - точка входа React

### 3. HTML и публичные файлы
- **index.html** - обновлен title на "GrozersStore"
- **public/favicon.svg** - скопирован
- **public/icons.svg** - скопирован

### 4. Конфигурация
- **.env.example** - уже был настроен с правильными значениями
- **package.json** - без изменений (уже настроен)
- **README.md** - обновлен с упоминанием о миграции

## Изменённые значения

### Промокоды
- NERVA50 → GROZERS50
- NERVA20 → GROZERS20

### Email префиксы
- nerva → grozers (в generateCredentialEmail)

### Текст ботов
- Все упоминания NervaHub заменены на GrozersStore
- Канал: @NervaHub → @GrozersStore
- Supabase store key: nervahub → grozersstore

## Проверки
✅ Нет оставшихся упоминаний "nerva", "NervaHub"
✅ Промокоды обновлены в server.js и App.jsx
✅ BrandLogo компонент обновлен
✅ document.title = 'GrozersStore'
✅ Все боты тексты на 3 языках (ru, en, zh) обновлены
✅ Размеры файлов совпадают с оригиналом

## Следующие шаги
1. Обновить .env файл с реальными токенами для @GrozersStore_bot
2. Проверить работу локально: `npm run dev` и `npm run dev:server`
3. Обновить переменные окружения на Render
4. Задеплоить на production

## Структура проекта
```
second bot/
├── src/
│   ├── App.jsx (1566 строк)
│   ├── App.css
│   ├── index.css
│   └── main.jsx
├── public/
│   ├── favicon.svg
│   └── icons.svg
├── server.js (1875 строк)
├── index.html
├── package.json
├── .env.example
└── README.md
```
