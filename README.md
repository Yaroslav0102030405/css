# Полная шпаргалка по CSS

## Основы CSS

### Синтаксис CSS

CSS-правило состоит из селектора и блока объявлений:

```css
селектор {
  свойство: значение;
  свойство: значение;
}
```

### Способы подключения CSS

1. **Встроенные стили** (Inline CSS):
```html
<p style="color: red; font-size: 20px;">Текст с красным цветом</p>
```

2. **Внутренние стили** (Internal CSS):
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

## Селекторы CSS

### Основные типы селекторов

1. **Селектор элемента**:
```css
p {
  color: blue;
}
```

2. **Селектор класса**:
```css
.my-class {
  color: green;
}
```

3. **Селектор идентификатора**:
```css
#my-id {
  color: red;
}
```

4. **Универсальный селектор**:
```css
* {
  margin: 0;
  padding: 0;
}
```

### Комбинаторы

1. **Потомки** (пробел):
```css
div p {
  color: red; /* Все параграфы внутри div */
}
```

2. **Дочерние элементы** (>):
```css
div > p {
  color: blue; /* Только прямые дочерние параграфы div */
}
```

3. **Смежные элементы** (+):
```css
h1 + p {
  color: green; /* Параграф, следующий сразу за h1 */
}
```

4. **Родственные элементы** (~):
```css
h1 ~ p {
  color: purple; /* Все параграфы после h1 на том же уровне */
}
```

### Псевдоклассы

```css
a:hover {
  color: red; /* Цвет ссылки при наведении */
}

p:first-child {
  font-weight: bold; /* Первый дочерний элемент p */
}

input:focus {
  border: 2px solid blue; /* Стиль при фокусе на поле ввода */
}
```

### Псевдоэлементы

```css
p::first-line {
  font-weight: bold; /* Первая строка параграфа */
}

p::before {
  content: "»"; /* Добавляет контент перед каждым параграфом */
}

p::after {
  content: "«"; /* Добавляет контент после каждого параграфа */
}
```

## Цвета и фоны

### Цвета

```css
p {
  color: red; /* Именованный цвет */
  color: #ff0000; /* Шестнадцатеричный код */
  color: rgb(255, 0, 0); /* RGB */
  color: rgba(255, 0, 0, 0.5); /* RGBA (с прозрачностью) */
  color: hsl(0, 100%, 50%); /* HSL */
  color: hsla(0, 100%, 50%, 0.5); /* HSLA (с прозрачностью) */
}
```

### Фоны

```css
div {
  background-color: lightblue; /* Цвет фона */
  background-image: url('image.jpg'); /* Фоновое изображение */
  background-repeat: no-repeat; /* Повторение фона */
  background-position: center; /* Позиция фона */
  background-size: cover; /* Размер фона */
  background-attachment: fixed; /* Фиксированный фон */
  
  /* Сокращенная запись */
  background: lightblue url('image.jpg') no-repeat center/cover fixed;
}
```

## Текст и шрифты

### Свойства текста

```css
p {
  color: #333; /* Цвет текста */
  text-align: center; /* Выравнивание текста */
  text-decoration: underline; /* Оформление текста */
  text-transform: uppercase; /* Трансформация текста */
  text-indent: 20px; /* Отступ первой строки */
  line-height: 1.5; /* Высота строки */
  letter-spacing: 2px; /* Расстояние между буквами */
  word-spacing: 5px; /* Расстояние между словами */
  white-space: nowrap; /* Обработка пробелов */
  text-shadow: 2px 2px 4px #000; /* Тень текста */
}
```

### Шрифты

```css
body {
  font-family: 'Arial', sans-serif; /* Семейство шрифтов */
  font-size: 16px; /* Размер шрифта */
  font-weight: bold; /* Жирность шрифта */
  font-style: italic; /* Стиль шрифта */
  font-variant: small-caps; /* Вариант шрифта */
  
  /* Сокращенная запись */
  font: italic bold 16px/1.5 'Arial', sans-serif;
}
```

### Подключение веб-шрифтов

```css
@font-face {
  font-family: 'MyFont';
  src: url('myfont.woff2') format('woff2'),
       url('myfont.woff') format('woff');
}

body {
  font-family: 'MyFont', sans-serif;
}
```

## Блочная модель (Box Model)

### Размеры элементов

```css
div {
  width: 300px; /* Ширина */
  height: 200px; /* Высота */
  max-width: 100%; /* Максимальная ширина */
  min-height: 100px; /* Минимальная высота */
  box-sizing: border-box; /* Включает padding и border в общий размер */
}
```

### Отступы и границы

```css
div {
  margin: 10px; /* Внешний отступ со всех сторон */
  margin-top: 20px; /* Верхний отступ */
  margin: 10px 20px 30px 40px; /* top, right, bottom, left */
  
  padding: 10px; /* Внутренний отступ со всех сторон */
  padding: 10px 20px; /* top/bottom, left/right */
  
  border: 1px solid black; /* Граница со всех сторон */
  border-width: 1px 2px 3px 4px; /* top, right, bottom, left */
  border-style: solid dashed dotted double;
  border-color: red green blue yellow;
  border-radius: 10px; /* Скругление углов */
  
  outline: 1px solid red; /* Контур (не влияет на размеры) */
}
```

## Позиционирование

### Типы позиционирования

```css
div {
  position: static; /* По умолчанию */
  position: relative; /* Относительное позиционирование */
  position: absolute; /* Абсолютное позиционирование */
  position: fixed; /* Фиксированное позиционирование */
  position: sticky; /* Липкое позиционирование */
  
  top: 10px;
  right: 20px;
  bottom: 30px;
  left: 40px;
  
  z-index: 10; /* Порядок наложения элементов */
}
```

### Плавающие элементы

```css
img {
  float: left; /* Обтекание слева */
  float: right; /* Обтекание справа */
  float: none; /* Отключение обтекания */
}

.clearfix::after {
  content: "";
  display: table;
  clear: both; /* Очистка обтекания */
}
```

## Flexbox

```css
.container {
  display: flex; /* Включение flexbox */
  flex-direction: row; /* row, row-reverse, column, column-reverse */
  flex-wrap: wrap; /* nowrap, wrap, wrap-reverse */
  flex-flow: row wrap; /* Сокращение для direction и wrap */
  
  justify-content: space-between; /* Выравнивание по главной оси */
  /* flex-start, flex-end, center, space-around, space-evenly */
  
  align-items: center; /* Выравнивание по поперечной оси */
  /* flex-start, flex-end, center, stretch, baseline */
  
  align-content: space-between; /* Выравнивание строк при wrap */
  /* flex-start, flex-end, center, space-between, space-around, stretch */
  
  gap: 10px; /* Отступы между flex-элементами */
}

.item {
  flex-grow: 1; /* Фактор роста */
  flex-shrink: 0; /* Фактор сжатия */
  flex-basis: 200px; /* Базовый размер */
  
  flex: 1 0 200px; /* Сокращение для grow, shrink, basis */
  
  align-self: flex-end; /* Индивидуальное выравнивание */
  /* auto, flex-start, flex-end, center, baseline, stretch */
  
  order: 2; /* Порядок элемента */
}
```

## CSS Grid

```css
.container {
  display: grid; /* Включение grid */
  
  grid-template-columns: 1fr 2fr 1fr; /* Определение колонок */
  grid-template-rows: 100px auto 100px; /* Определение строк */
  
  grid-template-areas: 
    "header header header"
    "sidebar content content"
    "footer footer footer"; /* Именованные области */
  
  gap: 10px; /* Отступы между ячейками */
  column-gap: 15px; /* Отступы между колонками */
  row-gap: 20px; /* Отступы между строками */
  
  justify-items: center; /* Выравнивание элементов по горизонтали */
  align-items: center; /* Выравнивание элементов по вертикали */
  
  justify-content: space-between; /* Выравнивание сетки по горизонтали */
  align-content: space-between; /* Выравнивание сетки по вертикали */
}

.item {
  grid-column: 1 / 3; /* Начальная / конечная колонка */
  grid-row: 2 / 4; /* Начальная / конечная строка */
  
  /* Или с использованием span */
  grid-column: 1 / span 2; /* Занимает 2 колонки */
  
  grid-area: header; /* Размещение в именованной области */
  
  justify-self: center; /* Индивидуальное выравнивание по горизонтали */
  align-self: center; /* Индивидуальное выравнивание по вертикали */
}
```

## Трансформации и переходы

### Трансформации

```css
.element {
  transform: translateX(20px); /* Сдвиг по X */
  transform: translateY(20px); /* Сдвиг по Y */
  transform: translate(20px, 20px); /* Сдвиг по X и Y */
  
  transform: scale(1.5); /* Масштабирование */
  transform: scaleX(1.5); /* Масштабирование по X */
  transform: scaleY(1.5); /* Масштабирование по Y */
  
  transform: rotate(45deg); /* Поворот */
  
  transform: skewX(10deg); /* Наклон по X */
  transform: skewY(10deg); /* Наклон по Y */
  
  /* Комбинирование трансформаций */
  transform: translate(20px, 20px) rotate(45deg) scale(1.5);
  
  transform-origin: center; /* Точка трансформации */
}
```

### Переходы

```css
.element {
  transition-property: all; /* Свойства для перехода */
  transition-duration: 0.5s; /* Длительность */
  transition-timing-function: ease-in-out; /* Функция времени */
  transition-delay: 0.2s; /* Задержка */
  
  /* Сокращенная запись */
  transition: all 0.5s ease-in-out 0.2s;
  
  /* Несколько переходов */
  transition: 
    color 0.3s ease,
    background-color 0.5s ease-in-out;
}
```

## Анимации

```css
/* Определение анимации */
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
  animation-name: slide-in; /* Имя анимации */
  animation-duration: 1s; /* Длительность */
  animation-timing-function: ease-out; /* Функция времени */
  animation-delay: 0.5s; /* Задержка */
  animation-iteration-count: 3; /* Количество повторений (infinite для бесконечного) */
  animation-direction: alternate; /* Направление */
  animation-fill-mode: forwards; /* Состояние до/после анимации */
  animation-play-state: running; /* Состояние проигрывания */
  
  /* Сокращенная запись */
  animation: slide-in 1s ease-out 0.5s 3 alternate forwards;
}
```

## Медиа-запросы (адаптивный дизайн)

```css
/* Медиа-запрос для экранов шириной до 768px */
@media screen and (max-width: 768px) {
  body {
    font-size: 14px;
  }
  
  .container {
    width: 100%;
  }
}

/* Медиа-запрос для экранов шириной от 768px до 1024px */
@media screen and (min-width: 768px) and (max-width: 1024px) {
  .container {
    width: 90%;
  }
}

/* Медиа-запрос для печати */
@media print {
  .no-print {
    display: none;
  }
  
  body {
    font-size: 12pt;
  }
}

/* Медиа-запрос для ориентации устройства */
@media (orientation: portrait) {
  /* Стили для портретной ориентации */
}

@media (orientation: landscape) {
  /* Стили для альбомной ориентации */
}
```

## Переменные CSS (Custom Properties)

```css
:root {
  --main-color: #3498db;
  --secondary-color: #2ecc71;
  --font-size: 16px;
  --spacing: 10px;
}

.element {
  color: var(--main-color);
  margin: var(--spacing);
  font-size: var(--font-size);
}

/* Переопределение переменных в медиа-запросах */
@media (max-width: 768px) {
  :root {
    --font-size: 14px;
    --spacing: 5px;
  }
}

/* Локальные переменные */
.special-section {
  --main-color: #e74c3c;
  color: var(--main-color); /* Будет использовать локальное значение */
}
```

## Специальные эффекты

### Тени

```css
.box {
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3); /* x, y, размытие, цвет */
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.2), 
              0 0 30px rgba(0, 0, 0, 0.1); /* Несколько теней */
  
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* x, y, размытие, цвет */
}
```

### Градиенты

```css
.element {
  /* Линейный градиент */
  background: linear-gradient(to right, red, blue);
  background: linear-gradient(45deg, red, blue);
  background: linear-gradient(to bottom right, red, yellow, blue);
  
  /* Радиальный градиент */
  background: radial-gradient(circle, red, blue);
  background: radial-gradient(ellipse at top left, red, yellow, blue);
  
  /* Конический градиент */
  background: conic-gradient(red, yellow, blue, red);
  background: conic-gradient(from 45deg, red, blue);
}
```

### Фильтры

```css
.image {
  filter: blur(5px); /* Размытие */
  filter: brightness(150%); /* Яркость */
  filter: contrast(200%); /* Контрастность */
  filter: grayscale(100%); /* Оттенки серого */
  filter: hue-rotate(90deg); /* Поворот оттенка */
  filter: invert(100%); /* Инверсия */
  filter: opacity(50%); /* Прозрачность */
  filter: saturate(200%); /* Насыщенность */
  filter: sepia(100%); /* Сепия */
  filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5)); /* Тень */
  
  /* Комбинирование фильтров */
  filter: contrast(150%) brightness(120%) sepia(30%);
}
```

## Практические приемы

### Центрирование элементов

```css
/* Центрирование блока по горизонтали */
.center-block {
  margin: 0 auto;
  width: 80%; /* Должна быть задана ширина */
}

/* Центрирование с помощью Flexbox */
.center-flex {
  display: flex;
  justify-content: center; /* По горизонтали */
  align-items: center; /* По вертикали */
}

/* Центрирование с помощью Grid */
.center-grid {
  display: grid;
  place-items: center;
}

/* Абсолютное центрирование */
.center-absolute {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### Скрытие элементов

```css
/* Полное скрытие (элемент не занимает место) */
.hidden {
  display: none;
}

/* Визуальное скрытие (элемент занимает место) */
.invisible {
  visibility: hidden;
}

/* Скрытие для скринридеров */
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

/* Прозрачность */
.transparent {
  opacity: 0;
}
```

### Обрезка текста

```css
/* Обрезка в одну строку с многоточием */
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* Обрезка многострочного текста */
.multiline-truncate {
  display: -webkit-box;
  -webkit-line-clamp: 3; /* Количество строк */
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

## Организация кода CSS

### Методологии именования классов

**BEM (Block, Element, Modifier)**
```css
.block {}
.block__element {}
.block--modifier {}
.block__element--modifier {}

/* Пример */
.card {}
.card__title {}
.card__image {}
.card--featured {}
```

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
```

### CSS-переменные для темизации

```css
:root {
  /* Светлая тема (по умолчанию) */
  --bg-color: #ffffff;
  --text-color: #333333;
  --accent-color: #3498db;
}

@media (prefers-color-scheme: dark) {
  :root {
    /* Темная тема */
    --bg-color: #222222;
    --text-color: #f5f5f5;
    --accent-color: #5dade2;
  }
}

/* Применение переменных */
body {
  background-color: var(--bg-color);
  color: var(--text-color);
}

.button {
  background-color: var(--accent-color);
}

/* Ручное переключение темы */
body.dark-theme {
  --bg-color: #222222;
  --text-color: #f5f5f5;
  --accent-color: #5dade2;
}
```
