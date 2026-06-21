# CLAUDE.md — проект beard.travel (Lend.html)

## Описание проекта
Лендинг тура выходного дня в Тверской области: «3 дня тишины у воды · 19 000 ₽».
Формат файла: обычный HTML (не bundled, без base64-упаковки ресурсов).
Бренд: **beard.travel**

## Файлы проекта
- `Lend.html` — основной файл лендинга (1847 строк, ~122 КБ)
- `logo.jpg` — логотип бренда (подключён в шапке и футере через `<img class="logo">`)
- `image-slot.js` — скрипт кастомного элемента `<image-slot>` (подключён в `<head>`, сам файл **отсутствует** в папке — нужно положить рядом)
- `assets/hero-kayaks.jpg` — фото для hero-секции (путь прописан в img, файл **отсутствует** в папке)

## Стек
- Чистый HTML5 + CSS3 + Vanilla JS (без фреймворков и бандлеров)
- Шрифты: Google Fonts CDN — Unbounded (заголовки), Onest (тело), Caveat (рукописный акцент)
- Кастомный элемент `<image-slot>` для слотов под фото

## Структура страницы (секции по порядку)

| # | Имя секции | HTML-маркер | id / class |
|---|-----------|-------------|------------|
| 1 | Промо-бар | `<div class="promo">` | — |
| 2 | Навигация | `<header class="nav">` | — |
| 3 | Hero | `<section class="hero">` | `data-screen-label="Hero"` |
| 4 | Триггеры доверия (Trust strip) | `<section class="trust-strip tight">` | — |
| 5 | Дедлайн-баннер | `<section class="tight">` | `data-screen-label="Дедлайн"` |
| 6 | Квиз «Подберём заезд» | `<section class="quiz-sec loose">` | `id="quiz"` |
| 7 | Программа (3 дня) | `<section class="program-sec loose">` | `id="program"` |
| 8 | Расписание заездов | `<section class="dates-sec">` | `id="dates"` |
| 9 | Что входит (Bento-сетка) | `<section id="why" class="loose">` | `id="why"` |
| 10 | Гарантии и возврат | `<section data-screen-label="Гарантии">` | — |
| 11 | О нас / О команде | `<section id="about" class="loose">` | `id="about"` |
| 12 | Отзывы | `<section id="reviews" class="reviews-sec">` | `id="reviews"` |
| 13 | FAQ | `<section id="faq" class="loose">` | `id="faq"` |
| 14 | Финальная форма заявки | `<section id="order" class="loose">` | `id="order"` |
| 15 | Контакты + карта | `<section id="contacts">` | `id="contacts"` |
| 16 | Футер | `<footer>` | — |
| 17 | Плавающие кнопки (мобайл) | `<div class="floating">` | — |
| 18 | Toast-уведомление | `<div class="toast">` | — |

## CSS-переменные (цвета бренда)

```css
:root {
  /* River — основной CTA */
  --moss:      #3A6F90;
  --moss-deep: #2C4A5E;
  --moss-soft: #5A8FB0;

  /* Светлая версия */
  --bark:      #5A8FB0;
  --bark-deep: #3A6F90;
  --bark-soft: #8AB3CC;

  /* Воздух / морская дымка */
  --sage:      #C6D8E3;
  --sage-mid:  #9DBACE;
  --mist:      #C6D8E3;
  --sky:       #9DBACE;
  --sky-deep:  #5A8FB0;

  /* Акцент — тёплый Sand */
  --honey:      #C9A876;
  --honey-soft: #DCC198;

  /* Нейтрали */
  --paper:   #F4EEE3;   /* фон страницы */
  --beige:   #EAE2D2;
  --beige-2: #DDD3BD;
  --beige-3: #C6BAA0;
  --ink:     #1B2A36;   /* основной текст */
  --ink-2:   #2C4A5E;
  --mute:    #6B7886;   /* второстепенный текст */
  --white:   #ffffff;
}
```

Шрифты:
```css
--fdisp: "Unbounded","Onest",ui-sans-serif   /* заголовки, цифры */
--fbody: "Onest","Unbounded",ui-sans-serif   /* тело */
--fhand: "Caveat",ui-serif                   /* рукописные акценты */
```

## Брейкпоинты мобильной адаптации

| Брейкпоинт | Что меняется |
|---|---|
| `@media (max-width: 1024px)` | Логотип: высота 64px, в футере 44px |
| `@media (max-width: 980px)` | Все сетки → 1 колонка; скрывается nav-links и телефон в шапке; trust-strip → 2 колонки; квиз-aside скрыт |
| `@media (max-width: 760px)` | deadline-banner → вертикальный стек |
| `@media (max-width: 600px)` | Мобильный вид: wrap 16px, hero compact, форма в 1 колонку, footer в 1 колонку; появляются floating-кнопки |
| `@media (max-width: 480px)` | Логотип: высота 56px, в футере 40px |

## Контакты в файле

- Телефон: **+7 (996) 635-51-48** → `tel:+79966355148`
- Telegram: **@strv_1** → `https://t.me/strv_1`
- VK (MAX): `https://vk.ru/strv4`
- Email: stevy359@yandex.ru (в файл ещё не добавлен)

Исполнитель: Тарасов Степан Евгеньевич, самозанятый (НПД), г. Тверь — **[в файл ещё не добавлен]** (нужно в футер)

## Формы и интеграции

**URL Google Apps Script:**
`https://script.google.com/macros/s/AKfycbxrMG2674OUac_VUlWafI1kAYblai9Ffg3DiSJcrDWghbXwVNK2MYu51-IoQZTpe1G3/exec`

Отправка: **[не реализована]** — нужно добавить fetch POST к обеим формам.

**Квиз** (`id="quiz"`, шаги 1–3):
- Шаг 1: с кем едете (Один / С парой / Друзья 3–5 / Корпоратив)
- Шаг 2: что важнее (Тишина и баня / Активности — каяки, сапы, лодки / Знакомства / Всё сразу)
- Шаг 3: форма-контакты
  - `q_name` — имя
  - `q_phone` — телефон/Telegram
  - `data-pick="channel"` — канал: Telegram / Звонок / MAX
  - `data-pick="dates"` — удобный месяц
  - `consent` — чекбокс ПДн (required)
- Отправка на бэкенд: **не реализована**

**Финальная форма** (`id="order"`, `class="leadform"`):
- `name` — имя (required)
- `phone` — телефон (required)
- `date` — select с датами заездов
- `guests` — select с количеством гостей
- `ch` — select: Telegram / MAX / Звонок
- `consent` — чекбокс ПДн (required)
- Отправка на бэкенд: **не реализована**

## Логотип

```css
.logo { height:72px; width:auto; object-fit:contain; display:block; border-radius:50% }
footer .logo { height:48px }
```

В HTML: `<img src="logo.jpg" alt="beard.travel — логотип" class="logo">` — шапка  
В HTML: `<img src="logo.jpg" alt="beard.travel — логотип" class="logo" loading="lazy">` — футер  
CSS `.brand-mark` (градиентный кружок) — **удалён**.

## Юридическая часть

- Модальные окна `#modal-privacy`, `#modal-pdn`, `#modal-offer` — **[не реализованы]**
- Cookies-баннер — **[не реализован]**
- Ссылки «Политика конфиденциальности» и «Условия возврата» в футере ведут на `href="#"` — **нужно подключить**
- Чекбокс согласия на ПДн: есть в квизе (шаг 3) и в финальной форме, оба `required`
- Данные исполнителя в футере: **[не добавлены]**

## Внешние ресурсы

- `https://fonts.googleapis.com` / `fonts.gstatic.com` — Google Fonts (preconnect)
- Google Fonts CSS: Unbounded (400/500/600/700), Onest (300/400/500/600/700), Caveat (500/600/700)
- `image-slot.js` — локальный скрипт, **файл отсутствует в папке**

## JS-логика (встроенный скрипт в конце body)

1. **Countdown** — обновляет все `[data-countdown="ДАТА"]` каждую секунду
2. **Hero timer** — таймер `#ht-days/hours/mins/secs`; цель: 27 июня 2026, 16:30
3. **Quiz** — навигация по шагам 1→3, выбор вариантов, pick-группы, экран «Заявка принята»
4. **Date filters** — фильтрация `.date-card` по `[data-cat]` через кнопки `.fchip`

## Правила работы с пользователем
- Пользователь не разработчик — объясняй простым языком
- Делай точечные правки, не переписывай файл целиком
- После каждой группы правок коротко отчитывайся
- Не «оптимизируй» соседний код без явной просьбы
- При любой проблеме сначала покажи пользователю, не исправляй сам

## История изменений

- **2026-06-21 (сессия 1)** — Создан CLAUDE.md. Анализ файла: выявлены плейсхолдеры контактов, отсутствие отправки форм и юридического блока.
- **2026-06-21 (сессия 2)** — Серия точечных правок:
  - Бренд «Лес & Вода» → **beard.travel** (7 мест: title, aria-label, brand-name ×2, подпись формы, контакты, копирайт)
  - Телефон **+7 (900) 123-45-67** → **+7 (996) 635-51-48** (7 мест)
  - Telegram **@les_i_voda** → **@strv_1** с реальными ссылками (6 мест, ник в контактах стал кликабельным)
  - WhatsApp → **MAX** (кнопка квиза, option формы, ссылка alt-call → vk.ru/strv4)
  - Hero H1: новый текст «Сплав на каяках, лес и тишина — в 3 часах от Москвы»
  - «байдарки/байдарках/байдарке» → **«каяки/каяках/каяке»** (7 мест по всему файлу)
  - Карточка «Шведский стол»: убрано «без графика», добавлено «по расписанию»
  - Блок «Что включено»: сокращён и актуализирован текст
  - Расписание дня 2: полностью заменено (6 новых пунктов с каяками)
  - Расписание дня 3: подъём 10:00 → 08:00 + добавлен завтрак 09:00
  - Логотип: `.brand-mark` CSS удалён → добавлен `.logo` + медиазапросы 1024px/480px; `<img src="logo.jpg">` в шапке и футере

## Что ещё нужно сделать

- [ ] Положить `logo.jpg` в папку рядом с `Lend.html`
- [ ] Положить `image-slot.js` рядом с `Lend.html` (или `assets/`)
- [ ] Положить `assets/hero-kayaks.jpg`
- [ ] Подключить отправку форм на Google Apps Script (fetch POST)
- [ ] Добавить данные исполнителя (Тарасов С.Е., самозанятый) в футер
- [ ] Реализовать модальные окна с текстами ПДн и офертой
- [ ] Добавить email stevy359@yandex.ru в контакты
