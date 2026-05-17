# ALOEMERO

Сайт-лендинг скульптурной мастерской **ALOEMERO** (Томск). Одностраничный визитка-сайт в bento-вёрстке: что делаем, где используем, материалы, сроки, контакты.

Боевая страница: <https://roman-purtow.ru/aloemero/>

> **Статус:** временно скрыт от поисковиков через `noindex`-теги — снимаем, когда заказчик даст добро на публикацию.

## Стек

- Чистый HTML5 + Tailwind CSS через CDN (JIT-сборка прямо в браузере)
- [GLightbox](https://github.com/biati-digital/glightbox) — лайтбокс для галереи
- Шрифт Inter с Google Fonts (только используемые веса)
- Хостинг — GitHub Pages

## Структура

```
.
├── index.html                 # вся страница в одном файле
├── assets/
│   ├── img/
│   │   ├── logo.jpg           # логотип в hero-блоке
│   │   ├── background.jpg     # резерв
│   │   └── gallery/01..12.jpg # 12 работ для двух фото-рядов
│   ├── icons/                 # favicons
│   └── source/
│       └── landing-copy.md    # исходный текст лендинга
├── apple-touch-icon.png
├── favicon.ico
├── site.webmanifest
└── README.md
```

## Локальный запуск

Сайт статический — достаточно открыть `index.html` в браузере. Чтобы корректно работали относительные пути (favicons, шрифты, GLightbox), удобнее поднять локальный сервер:

```bash
# Python 3
python -m http.server 8000

# Node.js (если установлен npx)
npx serve .
```

Откройте <http://localhost:8000>.

## Архитектура стилей

Все цвета централизованы как CSS-переменные в `:root` (палитра `stone-*` от Tailwind). Меняешь значение — обновляется по всему сайту.

Компонент-классы в `@layer components` (внутри `<style type="text/tailwindcss">`):

| Класс | Назначение |
|---|---|
| `.bento-grid` | базовая bento-сетка (3 кол. на mobile / 6 кол. на desktop) |
| `.bento-pad` / `.bento-pad-lg` | унифицированные внутренние отступы карточек |
| `.card` / `.card-dark` | светлые и тёмные карточки с hover-эффектом |
| `.photo-tile` / `.gallery-tile` | квадратные фото-плитки галереи |
| `.cta-tile` | блоки контактного ряда |
| `.bento-title` / `.bento-title-lg` / `.bento-stat` | иерархия заголовков bento-карточек |
| `.label` / `.label-light` / `.label-on-color` | мелкие подписи-нумераторы |
| `.process-step` / `.process-arrow` | шаги «полного цикла» |

## Деплой

Изменения попадают на прод автоматически через GitHub Pages при пуше в `main`.

```bash
git add -A
git commit -m "..."
git push
```

## Контакты мастерской

- Telegram: [@aloemero](https://t.me/aloemero)
- Канал работ: [masterskaa_aloemero](https://t.me/masterskaa_aloemero)
- Телефон: 8 913 645 90 22
