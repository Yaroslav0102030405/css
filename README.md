# Повна шпаргалка CSS

## Основи CSS

### Синтаксис CSS

CSS-правило складається з селектора та блоку оголошень:

```css
селектор {
 властивість: значення; 
 властивість: значення;
}
```

### Способи підключення CSS

1. **Внутрішні стилі** (Internal CSS):
```html
<p style="color: red; font-size: 20px;">Текст с красным цветом</p>
```

2. **Зовнішні стилі** (Internal CSS):
```html
<head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>
```

3. **Внешние стили** (External CSS):
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

## Селектори CSS

### Основні типи селекторів

1. **Селектор елемента**:
```css
p {
  color: blue;
}
```

2. **Селектор класу**:
```css
.my-class {
  color: green;
}
```

3. **Селектор ідентифікатора**:
```css
#my-id {
  color: red;
}
```

4. **Універсальний селектор**:
```css
* {
  margin: 0;
  padding: 0;
}
```

### Комбінатори

1. **Нащадки** (пробел):
```css
div p {
  color: red; /* Усі параграфи всередині div */
}
```

2. **Дочірні елементи** (>):
```css
div > p {
  color: blue; /* Тільки прямі дочірні параграфи div */
}
```

3. **Сусідній** (+):
```css
h1 + p {
  color: green; /* Параграф, наступний відразу за h1 */
}
```

4. **Загальні** (~):
```css
h1 ~ p {
  color: purple; /* Усі параграфи після h1 на тому ж рівні */
}
```

### Псевдокласи

```css
a:hover {
  color: red; /* Колір посилання при наведенні */
}

p:first-child {
  font-weight: bold; /* Перший дочірній елемент p */
}

input:focus {
  border: 2px solid blue; /* Стиль при фокусі на полі введення */
}
```

### Псевдоелементи

```css
p::first-line {
  font-weight: bold; /* Перший рядок параграфа */
}

p::before {
  content: "»"; /* Додає контент перед кожним параграфом */
}

p::after {
  content: "«"; /* Додає контент після кожного параграфа */
}
```

## Кольори та фони

### Кольори

```css
p {
  color: red; /* Іменований колір */
  color: #ff0000; /* Шістнадцятковий код */
  color: rgb(255, 0, 0); /* RGB */
  color: rgba(255, 0, 0, 0.5); /* RGBA (з прозорістю) */
  color: hsl(0, 100%, 50%); /* HSL */
  color: hsla(0, 100%, 50%, 0.5); /* HSLA (з прозорістю) */
}
```

### Фони

```css
div {
  background-color: lightblue; /* Колір фона */
  background-image: url('image.jpg'); /* Фонове зображення */
  background-repeat: no-repeat; /* Повторення фону */
  background-position: center; /* Позиція фона */
  background-size: cover; /* Розмір фону */
  background-attachment: fixed; /* Фіксований фон */
  
  /* Скорочений запис */
  background: lightblue url('image.jpg') no-repeat center/cover fixed;
}
```

## Текст та шрифти

### Властивості тексту

```css
p { 
color: #333; /* Колір тексту */ 
text-align: center; /* Вирівнювання тексту */ 
text-decoration: underline; /* Оформлення тексту */ 
text-transform: uppercase; /* Трансформація тексту */ 
text-indent: 20px; /* Відступ першого рядка */ 
line-height: 1.5; /* Висота рядка */ 
letter-spacing: 2px; /* Відстань між літерами */ 
word-spacing: 5px; /* Відстань між словами */ 
white-space: nowrap; /* Обробка пробілів */ 
text-shadow: 2px 2px 4px #000; /* Тінь тексту */
}
```

### Шрифти

```css
body { 
font-family: 'Arial', sans-serif; /* Сімейство шрифтів */ 
font-size: 16px; /* Розмір шрифту */ 
font-weight: bold; /* Жирність шрифту */ 
font-style: italic; /* Стиль шрифту */ 
font-variant: small-caps; /* Варіант шрифту */ 

/* Скорочений запис */ 
font: italic bold 16px/1.5 'Arial', sans-serif;
}
```

### Підключення веб-шрифтів

```css
@font-face { 
font-family: 'MyFont'; 
src: url('myfont.woff2') format('woff2'), 
url('myfont.woff') format('woff');
}

body { 
font-family: 'MyFont', sans-serif;
}
````

## Блокова модель (Box Model)

### Розміри елементів

```css
div { 
width: 300px; /* Ширина */ 
height: 200px; /* Висота */ 
max-width: 100%; /* Максимальна ширина */ 
min-height: 100px; /* Мінімальна висота */ 
box-sizing: border-box; /* Включає padding та border у загальний розмір */
}
````

### Відступи та кордони

```css
div { 
margin: 10px; /* Зовнішній відступ з усіх боків */ 
margin-top: 20px; /* Верхній відступ */ 
margin: 10px 20px 30px 40px; /* top, right, bottom, left */ 

padding: 10px; /* Внутрішній відступ з усіх боків */ 
padding: 10px 20px; /* top/bottom, left/right */ 

border: 1px solid black; /* Кордон з усіх боків */ 
border-width: 1px 2px 3px 4px; /* top, right, bottom, left */ 
border-style: solid dashed dotted double; 
border-color: green blue yellow; 
border-radius: 10px; /* Скруглення кутів */ 

outline: 1px solid red; /* Контур (не впливає на розміри) */
}
````

## Позиціювання

### Типи позиціонування

```css
div { 
position: static; /* За замовчуванням */ 
position: relative; /* Відносне позиціонування */ 
position: absolute; /* Абсолютне позиціонування */ 
position: fixed; /* Фіксоване позиціонування */ 
position: sticky; /* Липке позиціонування */ 

top: 10px; 
right: 20px; 
bottom: 30px; 
left: 40px; 

z-index: 10; /* Порядок накладання елементів */
}
````

### Плаваючі елементи

```css
img { 
float: left; /* Обтікання зліва */ 
float: right; /* Обтікання праворуч */ 
float: none; /* Відключення обтікання */
}

.clearfix::after { 
content: ""; 
display: table; 
clear: both; /* Очищення обтікання */
}
````

## Flexbox

```css
.container { 
display: flex; /* Увімкнення flexbox */ 
flex-direction: row; /* row, row-reverse, column, column-reverse */ 
flex-wrap: wrap; /* nowrap, wrap, wrap-reverse */ 
flex-flow: row wrap; /* Скорочення для direction та wrap */ 

justify-content: space-between; /* Вирівнювання по головній осі */ 
/* flex-start, flex-end, center, space-around, space-evenly */ 

align-items: center; /* Вирівнювання по поперечній осі */ 
/* flex-start, flex-end, center, stretch, baseline */ 

align-content: space-between; /* Вирівнювання рядків при wrap */ 
/* flex-start, flex-end, center, space-between, space-around, stretch */ 

gap: 10px; /* Відступи між flex-елементами */
}

.item { 
flex-grow: 1; /* Фактор зростання */ 
flex-shrink: 0; /* Фактор стиснення */ 
flex-basis: 200px; /* Базовий розмір */ 

flex: 10 200px; /* Скорочення для grow, shrink, basis */ 

align-self: flex-end; /* Індивідуальне вирівнювання */ 
/* auto, flex-start, flex-end, center, baseline, stretch */ 

order: 2; /* Порядок елемента */
}
````

## CSS Grid

```css
.container { 
display: grid; /* Увімкнення grid */ 

grid-template-columns: 1fr 2fr 1fr; /* Визначення колонок */ 
grid-template-rows: 100px auto 100px; /* Визначення рядків */ 

grid-template-areas: 
"header header header" 
"sidebar content content" 
"footer footer footer"; /* Іменовані області */ 

gap: 10px; /* Відступи між осередками */ 
column-gap: 15px; /* Відступи між колонками */ 
row-gap: 20px; /* Відступи між рядками */ 

justify-items: center; /* Вирівнювання елементів по горизонталі */ 
align-items: center; /* Вирівнювання елементів по вертикалі */ 

justify-content: space-between; /* Вирівнювання сітки по горизонталі */ 
align-content: space-between; /* Вирівнювання сітки по вертикалі */
}

.item { 
grid-column: 1/3; /* Початкова / кінцева колонка */ 
grid-row: 2/4; /* Початковий / кінцевий рядок */ 

/* Або з використанням span */ 
grid-column: 1/span 2; /* Займає 2 колонки */ 

grid-area: header; /* Розміщення в іменованій області */ 

justify-self: center; /* Індивідуальне вирівнювання по горизонталі */ 
align-self: center; /* Індивідуальне вирівнювання по вертикалі */
}
````

## Трансформації та переходи

### Трансформації

```css
.element { 
transform: translateX(20px); /* Зсув по X */ 
transform: translateY(20px); /* Зсув по Y */ 
transform: translate(20px, 20px); /* Зсув по X та Y */ 

transform: scale(1.5); /* Масштабування */ 
transform: scaleX(1.5); /* Масштабування за X */ 
transform: scaleY(1.5); /* Масштабування за Y */ 

transform: rotate(45deg); /* Поворот */ 

transform: skewX(10deg); /* Нахил по X */ 
transform: skewY(10deg); /* Нахил Y */ 

/* Комбінування трансформацій */ 
transform: translate(20px, 20px) rotate(45deg) scale(1.5); 

transform-origin: center; /* Точка трансформації */
}
````

### Переходи

```css
.element { 
transition-property: all; /* Властивості для переходу */ 
transition-duration: 0.5s; /* Тривалість */ 
transition-timing-function: ease-in-out; /* Функція часу */ 
transition-delay: 0.2s; /* Затримка */ 

/* Скорочений запис */ 
transition: all 0.5s ease-in-out 0.2s; 

/* Кілька переходів */ 
transition: 
color 0.3s ease, 
background-color 0.5s ease-in-out;
}
````

## Анімації

```css
/* Визначення анімації */
@keyframes slide-in { 
0% { 
transform: translateX(-100%); 
opacity: 0; 
} 
100% { 
transform: translateX(0); 
opacity: 1; 
}
}

.element { 
animation-name: slide-in; /* Ім'я анімації */ 
animation-duration: 1s; /* Тривалість */ 
animation-timing-function: ease-out; /* Функція часу */ 
animation-delay: 0.5s; /* Затримка */ 
animation-iteration-count: 3; /* Кількість повторень (infinite для нескінченного) */ 
animation-direction: alternate; /* Напрямок */ 
animation-fill-mode: forwards; /* Стан до/після анімації */ 
animation-play-state: running; /* Стан програвання */ 

/* Скорочений запис */ 
animation: slide-in 1s ease-out 0.5s 3 alternate forwards;
}
````

## Медіа-запити (адаптивний дизайн)

```css
/* Медіа-запит для екранів шириною до 768px */
@media screen and (max-width: 768px) { 
body { 
font-size: 14px; 
} 

.container { 
width: 100%; 
}
}

/* Медіа-запит для екранів шириною від 768px до 1024px */
@media screen and (min-width: 768px) and (max-width: 1024px) { 
.container { 
width: 90%; 
}
}

/* Медіа-запит для друку */
@media print { 
.no-print { 
display: none; 
} 

body { 
font-size: 12pt; 
}
}

/* Медіа-запит для орієнтації пристрою */
@media (orientation: portrait) { 
/* Стилі для портретної орієнтації */
}

@media (orientation: landscape) { 
/* Стилі для альбомної орієнтації */
}
````

## Змінні CSS (Custom Properties)

```css
:root { 
--main-color: #3498db; 
--secondary-color: #2ecc71; 
--font-size: 16px; 
--spacing: 10px;
}

.element { 
color: var(-main-color); 
margin: var(--spacing); 
font-size: var(--font-size);
}

/* Перевизначення змінних у медіа-запитах */
@media (max-width: 768px) { 
:root { 
--font-size: 14px; 
--spacing: 5px; 
}
}

/* Локальні змінні */
.special-section { 
--main-color: #e74c3c; 
color: var(-main-color); /* Використовуватиме локальне значення */
}
````

## Спеціальні ефекти

### Тіні

```css
.box { 
box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3); /* x, y, розмиття, колір */ 
box-shadow: 0 0 15px rgba(0, 0, 0, 0.2), 
0 0 30px rgba(0, 0, 0, 0.1); /* Кілька тіней */ 

text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* x, y, розмиття, колір */
}
````

### Градієнти

```css
.element { 
/* Лінійний градієнт */ 
background: linear-gradient(to right, red, blue); 
background: linear-gradient(45deg, red, blue); 
background: linear-gradient(to bottom right, red, yellow, blue); 

/* Радіальний градієнт */ 
background: radial-gradient( circle, red, blue); 
background: radial-gradient(ellipse at top left, red, yellow, blue); 

/* Конічний градієнт */ 
background: conic-gradient(red, yellow, blue, red); 
background: conic-gradient (від 45deg, red, blue);
}
````

### Фільтри

```css
.image { 
filter: blur(5px); /* Розмиття */ 
filter: brightness(150%); /* Яскравість */ 
filter: contrast(200%); /* Контрастність */ 
filter: grayscale(100%); /* Відтінки сірого */ 
filter: hue-rotate(90deg); /* Поворот відтінку */ 
filter: invert(100%); /* Інверсія */ 
filter: opacity(50%); /* Прозорість */ 
filter: saturate(200%); /* Насиченість */ 
filter: sepia(100%); /* Сепія */ 
filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5)); /* Тінь */ 

/* Комбінування фільтрів */ 
filter: contrast(150%) brightness(120%) sepia(30%);
}
````

## Практичні прийоми

### Центрування елементів

```css
/* Центрування блоку по горизонталі */
.center-block { 
margin: 0 auto; 
width: 80%; /* Повинна бути задана ширина */
}

/* Центрування за допомогою Flexbox */
.center-flex { 
display: flex; 
justify-content: center; /* По горизонталі */ 
align-items: center; /* По вертикалі */
}

/* Центрування за допомогою Grid */
.center-grid { 
display: grid; 
place-items: center;
}

/* Абсолютне центрування */
.center-absolute { 
position: absolute; 
top: 50%; 
left: 50%; 
transform: translate(-50%, -50%);
}
````

### Приховування елементів

```css
/* Повне приховування (елемент не займає місце) */
.hidden { 
display: none;
}

/* Візуальне приховування (елемент займає місце) */
.invisible { 
visibility: hidden;
}

/* Приховування для скринридерів */
.visually-hidden { 
position: absolute; 
width: 1px; 
height: 1px; 
margin: -1px; 
padding: 0; 
overflow: hidden; 
clip: rect(0, 0, 0, 0); 
border: 0;
}

/* Прозорість */
.transparent { 
opacity: 0;
}
````

### Обрізка тексту

```css
/* Обрізка в один рядок з трьома крапками */
.truncate { 
white-space: nowrap; 
overflow: hidden; 
text-overflow: ellipsis;
}

/* Обрізання багаторядкового тексту */
.multiline-truncate { 
display: -webkit-box; 
-webkit-line-clamp: 3; /* Кількість рядків */ 
-webkit-box-orient: vertical; 
overflow: hidden;
}
````

## Організація коду CSS

### Методології іменування класів

**BEM (Block, Element, Modifier)**
```css
.block {}
.block__element {}
.block --modifier {}
.block__element--modifier {}

/* Приклад */
.card {}
.card__title {}
.card__image {}
.card--featured {}
````

**SMACSS (Scalable and Modular Architecture for CSS)**
```css
/* Base */
body, h1, p {}

/* Layout */
.l-header, .l-sidebar {}

/* Module */
.btn {}
.btn-primary {}

/* State */
.is-active, .is-hidden {}

/* Theme */
.theme-dark .btn {}
````

### CSS-змінні для темизації

```css
:root { 
/* Світла тема (за замовчуванням) */ 
--bg-color: #ffffff; 
--text-color: #333333; 
--accent-color: #3498db;
}

@media (prefers-color-scheme: dark) { 
:root { 
/* Темна тема */ 
--bg-color: #222222; 
--text-color: #f5f5f5; 
--accent-color: #5dade2; 
}
}

/* Застосування змінних */
body { 
background-color: var(-bg-color); 
color: var(--text-color);
}

.button { 
background-color: var(--accent-color);
}

/* Ручне перемикання теми */
body.dark-theme { 
--bg-color: #222222; 
--text-color: #f5f5f5; 
--accent-color: #5dade2;
}
````
