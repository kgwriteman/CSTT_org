# CSTT — портал по Counter-Strike 2

React + Vite. Данные, вход администратора и картинки — Supabase.

## 1. Supabase (один раз)
1. Создайте проект на supabase.com.
2. SQL Editor → вставьте содержимое `supabase/schema.sql` → Run.
3. Authentication → Users → Add user: ваш email и пароль (это администратор).
4. Authentication → Sign In / Providers → отключите «Allow new users to sign up», иначе любой сможет зарегистрироваться и редактировать данные.
5. Project Settings → API: скопируйте Project URL и anon public key.

## 2. Запуск
```
cp .env.example .env     # впишите URL и ключ
npm install
npm run dev              # http://localhost:5173
```
Админка: `http://localhost:5173/#/admin`

## 3. Публикация
```
npm run build
```
Содержимое папки `dist` загрузите на любой хостинг (это статика, PHP и Node не нужны). Админка: `ваш-сайт/#/admin`.

## Структура
- `src/lib` — данные (Supabase), переводы RU/EN
- `src/components` — общие компоненты
- `src/pages` — страницы сайта
- `src/admin` — админ-панель (схема полей, CRUD)
- `src/styles` — CSS
- `supabase/schema.sql` — таблицы и права доступа
