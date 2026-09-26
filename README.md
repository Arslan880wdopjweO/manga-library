[README.md](https://github.com/user-attachments/files/32686868/README.md)
# MangaShelf

Учебный сайт-библиотека манги. Проект сдавался в два этапа:
**Assignment #1 (HTML & CSS Basics)** и **Assignment #2 (Advanced CSS —
Flexbox & Grid)**. Второй этап дополняет первый и не заменяет
существующие страницы и стиль.

**Студент:** Arslan Maratbekov
**Группа:** SE-2524

## Описание проекта

MangaShelf — это небольшая библиотека манги: каталог произведений,
страница об авторе, таблица оценок, форма отзыва, а также (начиная с
Assignment #2) страница с Grid-раскладкой, галерея обложек и страница
портфолио, где Flexbox и Grid используются вместе.

## Технологии

- HTML5
- CSS3
- **Flexbox** (навигация, ряд карточек, внутренняя структура карточек)
- **CSS Grid** (Grid Layout, Image Gallery, Portfolio)
- Без Bootstrap/Tailwind — весь CSS написан вручную в `styles.css`

## Список страниц

| Файл             | Задание           | Что показывает |
|------------------|--------------------|-----------------|
| `index.html`     | Assignment #1, Task 1 | Личная страница, профиль, списки |
| `catalog.html`   | Assignment #1, Task 2 + Assignment #2, Task 1 | Каталог: боковое меню на `float`, ряд карточек манги на **Flexbox** |
| `tribute.html`   | Assignment #1, Task 3 | Tribute page об Осаму Тэдзуке |
| `stats.html`     | Assignment #1, Task 4 | Таблица оценок (nth-child, highlight-row, colspan) |
| `feedback.html`  | Assignment #1, Task 4 | Форма обратной связи |
| `project.html`   | Assignment #1, Task 5 | Тема проекта, sitemap, wireframe |
| `grid.html`      | Assignment #2, Task 2 | Header/Sidebar/Main/Footer на **CSS Grid** (`grid-template-areas`) |
| `gallery.html`   | Assignment #2, Task 3 | Галерея из 9 обложек на **CSS Grid** с подписью при наведении |
| `portfolio.html` | Assignment #2, Task 4 | Header на Flexbox, макет на Grid, карточки проектов на Flexbox |
| `styles.css`     | —                  | Общий CSS-файл для всех страниц |
| `*.svg`          | —                  | Локальные изображения (обложки манги, портрет автора) |

## Где используется Flexbox

- **Навбар** (`.navbar` в `styles.css`, применяется на всех страницах):
  `display: flex; justify-content: space-between; align-items: center;`
  — логотип слева, ссылки справа, всё выровнено по вертикали.
  `flex-wrap: wrap` позволяет ссылкам переноситься на мобильных экранах.
- **Ряд карточек манги** на `catalog.html` (`.catalog`): `display: flex;
  flex-wrap: wrap; gap: 20px;` — карточки Moon Kingdom, Tokyo Letters и
  Nova Circuit стоят в ряд на десктопе.
- **Внутри каждой карточки** (`.manga-card`): `display: flex;
  flex-direction: column;` + `margin-top: auto` на кнопке — так кнопка
  всегда прижата к низу карточки, даже если текст разной длины.
- **Карточки проектов** на `portfolio.html` (`.project-card`): та же
  Flexbox-колонка с кнопкой внизу.

## Где используется CSS Grid

- **`grid.html`**: `.grid-page` — `display: grid;
  grid-template-areas: "header header" "sidebar main" "footer footer";`
  Шапка и подвал растянуты на всю ширину, меню слева, контент справа.
- **`gallery.html`**: `.gallery-grid` — `display: grid;
  grid-template-columns: repeat(3, 1fr); gap: 16px;` — девять обложек
  ровными рядами и колонками.
- **`portfolio.html`**: `.portfolio-layout` — `display: grid;
  grid-template-columns: 2fr 1fr;` делит страницу на колонку с
  проектами (слева) и колонку с информацией об авторе (справа).

## Как каждая задача выполнена

- **Task 0 (Navbar, Flexbox):** см. `.navbar` в `styles.css` — логотип
  слева, ссылки справа, `display: flex`.
- **Task 1 (Card row, Flexbox):** карточки манги на `catalog.html`
  переведены с обычных блоков на `.catalog`/`.manga-card` (Flexbox),
  добавлены изображения обложек и кнопки "Подробнее", одинаковая
  высота карточек и hover-эффект (подъём + тень).
- **Task 2 (Grid layout):** новая страница `grid.html` с
  `grid-template-areas` (header/sidebar/main/footer).
- **Task 3 (Image gallery):** новая страница `gallery.html`, 9
  обложек манги на CSS Grid, подпись появляется при наведении.
- **Task 4 (Flexbox + Grid портфолио):** новая страница
  `portfolio.html` — шапка на Flexbox, макет страницы на Grid,
  карточки внутри на Flexbox.

## Адаптивность

В `styles.css` есть два брейкпоинта:

- `@media (max-width: 800px)` — карточки манги по 2 в ряд, Grid Layout
  и Portfolio переходят в одну колонку, галерея — 2 колонки.
- `@media (max-width: 550px)` — навбар центрируется и ссылки идут
  блоками, карточки манги по одной в ряд, галерея — 1 колонка.

Float-раскладка `catalog.html` (Assignment #1, Task 2) по-прежнему не
использует Flexbox/Grid — только `float`, как и требовалось в первом
задании. Новые требования Assignment #2 нигде не используют float.

## Как запустить проект локально

1. Скачайте или склонируйте репозиторий.
2. Откройте `index.html` в браузере (двойной клик или "Открыть с
   помощью" → браузер).
3. Используйте навбар вверху, чтобы переходить между всеми
   страницами, включая новые: Grid Layout, Галерея, Портфолио.

## Публикация на GitHub Pages

1. Создайте репозиторий на [GitHub](https://github.com/).
2. Загрузите все файлы и папки, `index.html` должен остаться в корне.
3. Перейдите в **Settings → Pages**.
4. В разделе "Source" выберите ветку `main` и папку `/root`, сохраните.
5. Через минуту сайт будет доступен по адресу
   `https://ваш-логин.github.io/название-репозитория/`.

## Примечание

Форма обратной связи (`feedback.html`) демонстрационная — данные никуда
не отправляются.
