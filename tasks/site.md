# Task: Build a modern Petrenko Dev Apps website with Astro

Потрібно переробити існуючий сайт **Petrenko Dev Apps** на сучасний, легкий та візуально приємний сайт на базі **Astro**.

Сайт має виконувати дві основні функції:

1. Бути офіційною сторінкою розробника **Petrenko Dev** із контактами та підтримкою.
2. Презентувати мобільні застосунки та вести на окремі сторінки кожного застосунку.

Не потрібно робити сайт перевантаженим. Основний стиль — сучасний minimal / developer portfolio / product landing page із якісною типографікою, простором між елементами, мікроанімаціями та акуратними hover-ефектами.

## Tech

Використати:

- Astro
- TypeScript
- сучасний CSS
- CSS variables для дизайн-токенів
- responsive layout
- semantic HTML
- без важких UI-фреймворків, якщо вони не потрібні

JavaScript використовувати тільки там, де він реально потрібен.

Сайт повинен залишатися максимально легким та швидким.

---

# Pages

Створити три сторінки:

```text
/
 /medicine-reminder
 /dish-log
```

Бажано винести спільні елементи у компоненти:

```text
src/components/
src/layouts/
```

Наприклад:

```text
BaseLayout.astro
Header.astro
Footer.astro
AppShowcase.astro
AppSwitcher.astro
ContactSection.astro
```

Назви можна змінити, якщо структура проєкту цього потребує.

---

# 1. Home page

Головна сторінка повинна презентувати **Petrenko Dev Apps**.

Поточний текст приблизно такий:

```text
Petrenko Dev Apps

Welcome to the official support page for apps developed by Petrenko Dev.
```

Але не потрібно просто переносити його як README.

Зробити повноцінну сучасну landing page.

## Hero

У верхній частині:

**Petrenko Dev Apps**

Підзаголовок приблизно:

```text
Independent mobile apps built with care, simplicity and attention to detail.
```

або інший хороший англомовний текст зі схожим змістом.

Додати короткий текст про розробника:

```text
Hi, I'm Pavlo — a web developer who also builds mobile applications.
I create simple and useful tools designed to solve everyday problems.
```

Не потрібно створювати великий блок "About me". Це має бути легкий вступ.

Можна додати невеликий badge:

```text
Independent Developer
```

або:

```text
Web & Mobile Developer
```

---

# Header

Зробити компактний header.

Зліва:

```text
Petrenko Dev
```

Справа навігація:

```text
Apps
Support
```

Можна додати маленьку іконку або абстрактний developer mark, але без окремого логотипу.

Header може мати:

- легкий blur
- напівпрозорий background
- sticky positioning

але він не повинен займати багато місця.

---

# Support / Contact section

На головній сторінці зробити гарний блок підтримки.

Основний текст:

```text
Need help?

If you have a question, found an issue, or would like to share feedback about one of the apps, feel free to get in touch.
```

Email:

```text
petrenko.pavlo.dev@gmail.com
```

Email повинен бути клікабельним через:

```text
mailto:
```

Додати CTA:

```text
Contact Support
```

або:

```text
Send an Email
```

Також невеликим текстом зазначити:

```text
When contacting support, please include the app name, device and operating system version, and a short description of the issue.
```

Не потрібно показувати це великим списком — краще компактно та акуратно.

---

# Apps showcase

Найважливіший елемент головної сторінки.

У нижній частині головної сторінки зробити інтерактивний блок із двох частин.

Desktop layout:

```text
-------------------------------------------------
|                       |                       |
|   Medicine Reminder   |       Dish Log        |
|         50%           |         50%           |
|                       |                       |
-------------------------------------------------
```

Обидві картки/панелі повинні займати всю доступну ширину секції.

## Hover interaction

За замовчуванням:

```text
Medicine Reminder = 50%
Dish Log = 50%
```

При hover на Medicine Reminder:

```text
Medicine Reminder ≈ 65–70%
Dish Log ≈ 30–35%
```

При hover на Dish Log:

```text
Medicine Reminder ≈ 30–35%
Dish Log ≈ 65–70%
```

Перехід повинен бути плавний:

```css
transition: flex-grow 500ms cubic-bezier(...)
```

або інший якісний спосіб.

Не потрібно буквально розтягувати блок до 100% і повністю приховувати інший — залишити частину другого блоку видимою, щоб UI виглядав природно.

На touch/mobile hover-взаємодія не потрібна.

На mobile картки можна зробити одна під одною.

---

# Medicine Reminder card

Це мобільний застосунок на:

```text
React Native
```

Кольорова стилістика повинна асоціюватися з React / React Native.

Не обов'язково використовувати буквально стандартний React blue на всій картці.

Можна використати:

- темний navy / charcoal background
- cyan / React blue accents
- subtle glow
- gradient

Наприклад:

```text
#61DAFB
```

як accent.

Контент:

```text
Medicine Reminder

Medication reminders made simple.

React Native
```

Додати невеликий technology badge:

```text
React Native
```

Картка повністю клікабельна і веде на:

```text
/medicine-reminder
```

Додати placeholder для screenshot / phone mockup.

Наприклад:

```text
/public/images/medicine-reminder-placeholder.webp
```

Якщо файлу немає, створити акуратний CSS placeholder, щоб layout не ламався.

---

# Dish Log card

Це мобільний застосунок на:

```text
Flutter
```

Стилістика відповідно до Flutter.

Accent кольори можуть базуватися на:

```text
#02569B
#13B9FD
```

але використовувати їх сучасно та стримано.

Контент приблизно:

```text
Dish Log

Remember what you cooked and discover what to make next.

Flutter
```

Badge:

```text
Flutter
```

Вся картка веде на:

```text
/dish-log
```

Так само використати placeholder screenshot.

---

# App card microinteractions

На hover:

- зображення може трохи scale up
- background gradient може плавно змінюватися
- arrow icon може зсуватися вправо
- title може трохи зміщуватися
- accent glow може ставати сильнішим

Приклад поведінки:

```text
View app →
```

Arrow:

```text
→
```

на hover зміщується приблизно на `4–6px`.

Анімації повинні бути subtle.

Не робити flashy ефекти.

---

# 2. Medicine Reminder page

Створити окрему product landing page:

```text
/medicine-reminder
```

Ця сторінка повинна мати свою visual identity, натхненну React Native.

Не потрібно робити її копією головної.

## Hero

Приблизна структура:

```text
Medicine Reminder

Never miss your medication.

A simple mobile app designed to help you keep track of your medication schedule and reminders.
```

Technology badge:

```text
Built with React Native
```

CTA можна зробити:

```text
Get the app
```

Поки що, якщо немає реального store URL, CTA може бути disabled / placeholder або вести на `#`.

Не вигадувати реальні App Store / Google Play URLs.

---

# Medicine Reminder screenshot section

Зробити секцію для screenshots.

Поки що використати placeholders.

Наприклад 3 картки:

```text
Reminder screen
Medication schedule
Daily overview
```

Або просто графічні placeholders без конкретних підписів.

Структуру зробити так, щоб пізніше було легко замінити placeholder:

```text
/public/images/medicine-reminder/01.webp
/public/images/medicine-reminder/02.webp
/public/images/medicine-reminder/03.webp
```

Не вимагати наявності цих файлів.

---

# Medicine Reminder features

Додати невелику секцію:

```text
Simple reminders
Stay on schedule with clear medication reminders.

Medication overview
Keep your medications and schedules organized.

Designed for everyday use
A clean interface without unnecessary complexity.
```

Не потрібно вигадувати складний функціонал, якого може не бути.

---

# 3. Dish Log page

Створити:

```text
/dish-log
```

Стилістично ця сторінка повинна бути пов'язана з Flutter.

Hero:

```text
Dish Log

Keep track of the dishes you love to cook.

Dish Log helps you remember what you've cooked, when you cooked it, and makes it easier to decide what to make next.
```

Badge:

```text
Built with Flutter
```

---

# Dish Log screenshots

Так само підготувати screenshot area.

Placeholder paths:

```text
/public/images/dish-log/01.webp
/public/images/dish-log/02.webp
/public/images/dish-log/03.webp
```

Якщо зображень немає — використовувати красиві placeholders.

---

# Dish Log features

Можна показати:

```text
Track your dishes
Save dishes you cook regularly.

Cooking history
See when you last prepared a dish.

Tags & organization
Organize dishes so they're easy to find.
```

Не вигадувати функції, яких немає.

---

# Navigation between apps

На обох app pages унизу зробити секцію:

```text
Explore another app
```

Наприклад на Medicine Reminder:

```text
Dish Log
Built with Flutter
→
```

На Dish Log:

```text
Medicine Reminder
Built with React Native
→
```

Також має бути можливість повернутися на home.

---

# Visual design

Загальна дизайн-система сайту:

- сучасний minimal design
- багато whitespace
- rounded corners
- subtle gradients
- very subtle shadows
- clean typography
- responsive
- dark або dark-first дизайн

Бажано зробити загальний background приблизно:

```text
#090b10
```

або інший дуже темний neutral.

Cards:

```text
#11141b
```

Text:

```text
#f5f5f5
```

Muted:

```text
#9ca3af
```

Але створити CSS variables, а не розкидати hardcoded кольори по всіх компонентах.

Наприклад:

```css
:root {
  --background: ...;
  --surface: ...;
  --text: ...;
  --text-muted: ...;
  --border: ...;

  --react: #61dafb;
  --flutter: #13b9fd;
}
```

---

# Typography

Використати сучасний sans-serif.

Можна:

```text
Inter
Manrope
Geist
```

або system font stack.

Якщо використовується Google Font, не перевантажувати сайт багатьма font weights.

Hero typography повинна бути великою, але не надмірною.

Наприклад desktop:

```text
font-size: clamp(3rem, 7vw, 6rem);
```

---

# Background details

Можна використати дуже subtle декоративні елементи:

- blurred gradient blobs
- grid
- radial gradient
- noise-like CSS texture
- thin borders

Але background не повинен відволікати від контенту.

Не використовувати важкі canvas/WebGL effects.

---

# Animations

Додати невеликі entrance animations.

Наприклад:

- fade + translate hero
- cards fade in
- screenshot cards reveal

Можна реалізувати через CSS та IntersectionObserver.

Не використовувати animation library без необхідності.

Поважати:

```css
@media (prefers-reduced-motion: reduce)
```

і відключати складні animations для таких користувачів.

---

# Responsive behaviour

Desktop:

- широкий hero
- apps cards 50 / 50
- screenshots у горизонтальному layout

Tablet:

- layout адаптується без horizontal overflow

Mobile:

- app cards одна під одною
- hover flex effect вимкнений
- hero font smaller
- screenshots можна показувати горизонтальним scroll або вертикально

Перевірити мінімум:

```text
375px
768px
1440px
```

---

# Accessibility

Обов'язково:

- semantic HTML
- нормальний color contrast
- keyboard navigation
- `:focus-visible`
- app cards повинні бути справжніми `<a>`
- не робити click handlers на `<div>`
- meaningful aria labels, якщо потрібні
- alt для реальних screenshots

---

# SEO

Для кожної сторінки додати:

```html
<title>
<meta name="description">
```

Home:

```text
Petrenko Dev Apps
```

Medicine:

```text
Medicine Reminder — Petrenko Dev
```

Dish Log:

```text
Dish Log — Petrenko Dev
```

Додати базові Open Graph meta tags.

---

# Footer

На всіх сторінках:

```text
Petrenko Dev
```

Email:

```text
petrenko.pavlo.dev@gmail.com
```

і copyright:

```text
© {current year} Petrenko Dev
```

Рік не hardcode, отримувати програмно.

Також можна додати:

```text
Privacy
Support
```

Якщо окремих сторінок поки немає, не створювати dead links.

---

# Important design requirement

Особливу увагу приділити головній секції з двома apps.

Це має бути головний інтерактивний visual element сайту.

Поведінка повинна відчуватися приблизно так:

```text
default
[ Medicine 50% ][ Dish Log 50% ]

hover Medicine
[      Medicine 68%      ][ Dish 32% ]

hover Dish Log
[ Medicine 32% ][       Dish Log 68%       ]
```

Використати CSS flexbox.

Animation повинна бути smooth і premium-feeling.

При hover збільшувати не лише ширину, але й reveal додаткових деталей у активній картці, наприклад:

```text
Medication reminders made simple.
Built with React Native.
```

У неактивній картці другорядний текст може ставати менш помітним.

---

# Code quality

Після реалізації:

- не дублювати layout code
- винести повторювані UI pieces у компоненти
- CSS організувати логічно
- не залишати console errors
- не додавати зайві dependencies
- не ламати існуючу Astro configuration
- не видаляти існуючий deployment configuration
- перевірити production build

Запустити:

```bash
npm run build
```

або відповідну build-команду проєкту.

Виправити всі build errors.

---

# Expected result

У результаті повинен вийти невеликий, але завершений developer/product website:

```text
Petrenko Dev Apps

        ↓

About / Support

        ↓

┌──────────────────────────────┐
│ Medicine       │ Dish Log    │
│ React Native   │ Flutter     │
│                │             │
└──────────────────────────────┘
      interactive 50/50

        ↓

Footer
```

З окремими сучасними landing pages:

```text
/medicine-reminder
/dish-log
```

Сайт повинен виглядати як справжній сайт незалежного mobile developer, а не як README або стандартна документаційна сторінка.

Пріоритети:

1. Visual polish
2. Apps 50/50 interactive section
3. Typography and spacing
4. Subtle microanimations
5. Performance
6. Responsive behaviour
7. Clean Astro architecture
