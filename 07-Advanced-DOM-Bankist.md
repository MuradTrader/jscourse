Вот обработанный текст в формате Markdown, сохраненный в исходном виде без изменений:

```markdown
Ты профессиональный разработчик на javascript, и я хочу к тебе отправлять мои тексты, чтобы ты подстроил мои тексты для файла md в красивом виде, внимание на тексте не нужно ничего менять или добавлять это очень важно текст должен быть как есть.
ЕЩЕ РАЗ ПИШУ НЕ МЕНЯЙ ТЕКСТ, ВЕСЬ ТЕКСТ ДОЛЖЕН БЫТЬ В ИСХОДНОМ ФОРМАТЕ НИЧЕГО НЕ УПУСКАЙ!!!!! ЭТО ВАЖНО!

Вот мой текст:

## КАК НА САМОМ ДЕЛЕ РАБОТАЕТ DOM

Что такое DOM?
DOM — это интерфейс между HTML-документом (вашей веб-страницей) и JavaScript-кодом.

Благодаря DOM мы можем:

Изменять элементы (создавать, удалять, изменять).
Устанавливать стили, классы, атрибуты.
Реагировать на события (например, клики).

Пример:
document.querySelector("h1").textContent = "Привет, DOM!";
Этот код:
Находит элемент <h1>.
Изменяет его текстовое содержимое.

Как устроен DOM изнутри?
HTML-документ представляется в виде дерева DOM — структуры из узлов (nodes).
Каждый узел — это объект в JavaScript.

Типы узлов
DOM включает разные типы узлов:

Элемент (Element): Например, <div>, <h1>, <p>.
Текст (Text): Содержимое текста внутри элементов.
Комментарий (Comment): Комментарии в HTML (<!-- Comment -->).
Документ (Document): Корневой объект, представляющий весь HTML-документ.
Каждый узел имеет свойства и методы, чтобы взаимодействовать с ним.

Структура DOM API
Базовая схема:
Node — базовый тип.
Все узлы (Element, Text, Comment, Document) наследуют свойства и методы от Node.

Примеры методов:
textContent — получить/изменить текст узла.
childNodes — получить дочерние узлы.
parentNode — получить родительский узел.
cloneNode() — клонировать узел.

Element — тип для HTML-элементов.
Наследует всё от Node + добавляет свои свойства:
classList — работа с классами.
children — получить дочерние элементы.
innerHTML — получить/изменить HTML внутри элемента.
Методы:
append() — добавить дочерний элемент.
remove() — удалить элемент.
querySelector() — найти элемент.
HTML Element — конкретные элементы HTML (например, <button>, <img>).

Каждый HTML-элемент имеет свои уникальные свойства:
<img>: src, alt.
<a>: href.

Document — объект верхнего уровня.
Методы:
querySelector(), getElementById(), createElement().

EventTarget — базовый тип для событий.
Позволяет всем узлам (и window) использовать addEventListener.

Наследование в DOM:
Ключевая идея в DOM — это наследование.
Это значит, что дочерние типы узлов наследуют методы и свойства родительских.

Пример:
HTMLButtonElement (кнопка) наследует:

Всё от HTMLElement.
Всё от Element.
Всё от Node.

Поэтому у кнопки есть:
textContent (из Node).
classList (из Element).
onclick (из HTMLElement).

Как это работает на практике?
Пример работы с узлами
Создание нового элемента:
const newDiv = document.createElement("div"); // Создаем новый <div>
newDiv.textContent = "Привет, мир!"; // Устанавливаем текст
document.body.append(newDiv); // Добавляем в <body>

Удаление элемента:
const header = document.querySelector("h1");
header.remove(); // Удаляем заголовок

Прослушивание событий
Добавление обработчика событий:
const button = document.querySelector("button");
button.addEventListener("click", function () {
alert("Кнопка нажата!");
});

EventTarget: почему addEventListener работает?
addEventListener — метод базового типа EventTarget.
Этот тип является родителем для:
Node (а значит, всех узлов).

Window.
Благодаря наследованию, любой узел или window может слушать события.

Сравнение методов
Некоторые методы доступны на разных уровнях:
querySelector:
У Document — ищет элементы по всему документу.
У Element — ищет только внутри этого элемента.
Пример:
document.querySelector(".container"); // Весь документ
document.querySelector(".container").querySelector("h1"); // Только внутри .container

Итоги
DOM — это дерево объектов, представляющее HTML-документ.
Узлы (Node) имеют типы: Element, Text, Comment, Document.
Каждый тип узла наследует методы и свойства от родительских типов.
addEventListener работает на всех узлах благодаря EventTarget.

Вы сказали:
Расскажи подробно, я не совсем понял, я новичоков в программировании.
ChatGPT сказал:
Не волнуйтесь, давайте объясним всё шаг за шагом на более простом языке, чтобы стало понятно даже новичку.

Что такое DOM?
Представьте, что ваш HTML-документ — это дерево.

Каждая часть HTML — это ветка или лист.
DOM (Document Object Model) — это способ, как браузер превращает HTML в дерево объектов,
чтобы ваш JavaScript мог с ним работать.
Пример:
HTML-код:

<!DOCTYPE html>
<html>
<head>
  <title>Пример</title>
</head>
<body>
  <h1>Привет, мир!</h1>
  <p>Это параграф.</p>
</body>
</html>

В браузере это превращается в DOM-дерево:
Document
└── html
├── head
│ └── title ("Пример")
└── body
├── h1 ("Привет, мир!")
└── p ("Это параграф.")

Каждая строка (например, <h1>Привет, мир!</h1>) становится узлом (node),
с которым можно работать с помощью JavaScript.

Как JavaScript взаимодействует с DOM?
С помощью DOM API (интерфейса программирования) вы можете:

Находить элементы.
Изменять их.
Реагировать на действия пользователя.

Пример:
Найти элемент:
const header = document.querySelector("h1"); // Находит первый <h1>
console.log(header.textContent); // Выводит: Привет, мир!

Изменить текст:
header.textContent = "Привет, JavaScript!"; // Меняет текст в <h1>

Реагировать на клик:
header.addEventListener("click", () => {
alert("Вы нажали на заголовок!");
});

Что такое узлы (Nodes)?
Каждая часть HTML превращается в узел:

Элементы (Element): Это теги HTML (<h1>, <p>, <div>).
Текст (Text): Текст внутри тегов.
Комментарии (Comment): Комментарии в HTML (<!-- Пример -->).

Пример:
html

<h1>Привет!</h1>
<!-- Это комментарий -->

В DOM это:
php
Element: <h1>
└── Text: "Привет!"
Comment: <!-- Это комментарий -->

Наследование: почему все работает?
В DOM есть главная идея — наследование.
Это значит, что разные типы узлов "наследуют" свойства и методы от своих "родителей".

Представьте семейное древо:
У всех узлов есть общий "родитель" — Node.
Node даёт всем узлам базовые свойства, например:
textContent — получить или изменить текст внутри узла.
parentNode — узнать родителя узла.

Пример:
const header = document.querySelector("h1"); // Найти <h1>
console.log(header.textContent); // Это свойство от "Node".
console.log(header.parentNode); // Показывает родительский <body>.

Типы узлов
DOM организован в виде иерархии.
Вот главные типы:

Node — базовый тип.

Дает общие свойства (например, textContent, parentNode).

Element — узел для HTML-элементов.
Наследует всё от Node.
Дополнительно добавляет свойства для работы с HTML:
classList — управлять классами.
children — получить дочерние элементы.
innerHTML — изменить содержимое HTML.
Document — корневой узел.

Это весь HTML-документ.
Методы:
querySelector() — найти элемент.
createElement() — создать новый элемент.
Text — узел для текста внутри элементов.

Comment — узел для комментариев.

Как это работает на практике?

1. Найти элемент
   const title = document.querySelector("h1"); // Находим <h1>
   console.log(title.textContent); // "Привет, мир!"

2. Изменить элемент
   title.textContent = "Привет, JavaScript!"; // Меняем текст в <h1>

3. Создать новый элемент
   const newDiv = document.createElement("div"); // Создаем <div>
   newDiv.textContent = "Я новый элемент!";
   document.body.append(newDiv); // Добавляем его в конец <body>

4. Удалить элемент
   newDiv.remove(); // Удаляем только что созданный элемент

5. Добавить обработчик событий
   title.addEventListener("click", () => {
   alert("Вы нажали на заголовок!");
   });

Почему DOM работает так гибко?
Каждый элемент наследует свойства и методы:

Узлы (Node) дают базовые свойства (textContent, parentNode).
HTML-элементы (Element) добавляют методы для работы с HTML (classList, innerHTML).

Все узлы могут слушать события:
Это благодаря типу EventTarget, который даёт всем узлам метод addEventListener().

Итог: что вы должны понять?
DOM — это дерево объектов, представляющее HTML-документ.
Каждая часть HTML — это узел (Node):
Теги становятся Element.
Текст становится Text.
Вы можете взаимодействовать с DOM через методы и свойства:
Находить элементы (querySelector).
Изменять текст (textContent).
Добавлять события (addEventListener).

// ------------------------------------------------------------------------------- //

## ВЫБОР, СОЗДАНИЕ И УДАЛЕНИЕ ЭЛЕМЕНТОВ

1. Выбор элементов в DOM
   DOM (Document Object Model) — это структура, представляющая HTML-документ в виде дерева.
   Мы можем выбирать элементы этого дерева для взаимодействия с ними.

Выбор документа:
Самый верхний элемент в любом HTML-документе — это сам документ.

Чтобы выбрать весь документ, используйте:
const docElement = document.documentElement; // Корневой элемент (html)

Выбор head и body:
У вас есть встроенные способы выбрать основные части документа:
const head = document.head; // Тег <head>
const body = document.body; // Тег <body>

Использование querySelector:
Чтобы выбрать конкретный элемент:
const header = document.querySelector("header"); // Первый <header> на странице

Если вы хотите выбрать все элементы, соответствующие селектору:
const sections = document.querySelectorAll(".section"); // Все элементы с классом .section

Эти методы возвращают:
querySelector — одиночный элемент.
querySelectorAll — список узлов (NodeList), который не обновляется автоматически при изменении DOM.

Другие методы выбора:
По ID:
const section = document.getElementById("section1");

По имени тега:
const buttons = document.getElementsByTagName("button"); // Все <button>
Возвращает HTMLCollection — коллекцию, которая обновляется автоматически при изменении DOM.

По имени класса:
const btns = document.getElementsByClassName("btn"); // Все элементы с классом .btn
Тоже возвращает HTMLCollection.

Сравнение NodeList и HTMLCollection
NodeList не обновляется автоматически.
HTMLCollection обновляется, если элементы в DOM изменяются (удаляются или добавляются).
Пример:
const buttons = document.getElementsByTagName("button");
console.log(buttons.length); // 3

// Удалим один из кнопок
document.querySelector("button").remove();
console.log(buttons.length); // Теперь 2 (HTMLCollection обновилось)

2. Создание и вставка элементов
   Мы можем создавать новые элементы программно и добавлять их в DOM.

Создание элемента
Используем document.createElement():
const newDiv = document.createElement("div"); // Создаем <div>
newDiv.textContent = "Я новый элемент!";

Добавление классов и атрибутов:
newDiv.classList.add("my-class"); // Добавляем класс
newDiv.setAttribute("id", "unique-id"); // Устанавливаем атрибут

Вставка в DOM:
append() и prepend() — добавляют элемент как первый или последний дочерний элемент:
document.body.append(newDiv); // Добавляем в конец body
document.body.prepend(newDiv); // Добавляем в начало body

before() и after() — вставляют элемент перед или после выбранного:
const header = document.querySelector("header");
header.before(newDiv); // Перед header
header.after(newDiv); // После header

cloneNode() — создает копию элемента:
const clonedDiv = newDiv.cloneNode(true); // Клонирует div и его содержимое
document.body.append(clonedDiv);

3. Удаление элементов
   Удалить элемент можно несколькими способами.

Метод remove()
Прямое удаление:
newDiv.remove(); // Удаляет элемент из DOM

Удаление через родителя:
Ранее использовался метод removeChild:
document.body.removeChild(newDiv); // Удаляет newDiv из body

4. Практический пример
   Создадим баннер с кнопкой, который можно закрыть:

// Создаем элемент
const banner = document.createElement("div");
banner.classList.add("banner");
banner.innerHTML = `

  <p>Мы используем куки для улучшения работы сайта.</p>
  <button class="close-btn">Закрыть</button>
`;

// Добавляем в DOM
document.body.prepend(banner);

// Добавляем событие для закрытия
document.querySelector(".close-btn").addEventListener("click", () => {
banner.remove();
});

5. Использование insertAdjacentHTML
   Это быстрый способ добавить HTML в DOM:
   document.body.insertAdjacentHTML("beforeend", "<p>Пример текста</p>");

Методы:
"beforebegin" — перед элементом.
"afterbegin" — внутри элемента, перед первым дочерним.
"beforeend" — внутри элемента, после последнего дочернего.
"afterend" — после элемента.

Пример:
const header = document.querySelector("header");
header.insertAdjacentHTML("beforeend", "<p>Это текст внутри header</p>");

Итог
Вы научились:
Выбирать элементы.
Создавать и вставлять элементы.
Удалять элементы.

Различия document от documentElement:
document и document.documentElement — это два разных объекта в JavaScript,
которые относятся к DOM, но представляют разные части документа.
Давайте разберем, зачем нужен documentElement и чем он отличается от document.

Что такое document?
document — это глобальный объект, представляющий весь HTML-документ.
Он предоставляет интерфейс для работы со всем DOM-деревом.

С помощью document вы можете:
Доступаться к элементам на странице (например, document.querySelector()).
Манипулировать DOM (создавать, изменять или удалять элементы).
Получать информацию о документе (например, заголовок через document.title).
Однако, сам document не является DOM-элементом.
Это просто объект, представляющий весь документ.

Что такое document.documentElement?
document.documentElement — это самый верхний элемент в DOM-дереве.
В HTML-документе это всегда <html>:

<html>
  <head>...</head>
  <body>...</body>
</html>
Когда вы обращаетесь к document.documentElement, вы фактически получаете сам элемент <html>.

Пример:
console.log(document.documentElement); // <html>...</html>

Почему мы не можем просто использовать document?
Хотя document представляет весь документ, он не является самим элементом <html>.

Это значит, что вы не можете, например:
Манипулировать стилями документа через document.style.
Работать с атрибутами, как это делается с DOM-элементами.

Пример различий:
// Попытка изменить стиль через document (ошибка)
document.style.backgroundColor = "red"; // ❌ Ошибка

// Изменение стиля через documentElement (работает)
document.documentElement.style.backgroundColor = "red"; // ✅ Работает

Когда нужен documentElement?
documentElement нужен, когда вам нужно работать с самим <html> или применить изменения ко всему документу.

Пример 1: Изменение стилей всего документа
Вы хотите изменить фон всего документа:
document.documentElement.style.backgroundColor = "lightblue";

Пример 2: Получение информации о прокрутке
Параметры прокрутки, такие как scrollTop или scrollHeight,
лучше всего считывать через document.documentElement, а не через document.

Пример:
console.log(document.documentElement.scrollTop); // Текущая вертикальная прокрутка

Пример 3: Подключение CSS через атрибуты
Вы можете работать с атрибутами элемента <html>.

Например:
document.documentElement.setAttribute("lang", "en"); // Устанавливаем язык документа

Краткое сравнение:
Свойство document:
Что оно представляет - Объект, представляющий весь документ
Когда использовать - Для работы с DOM через методы (например, querySelector)
Свойство document.documentElement:
Что оно представляет - Самый верхний элемент (<html>)
Когда использовать - Для доступа и манипуляций с элементом <html>

Итог:
document — это объект для работы с документом,
а document.documentElement — это конкретный элемент <html>.
Если вам нужно работать с верхним уровнем DOM
(например, изменить стиль документа, атрибуты <html> или получить размеры прокрутки),
используйте document.documentElement.

// ------------------------------------------------------------------------------- //

## СТИЛИ, АТРИБУТЫ И КЛАССЫ

Что мы будем изучать?
В этой лекции речь идет о том, как:

Работать со стилями элементов (CSS через JavaScript).
Управлять атрибутами HTML-элементов.
Использовать data-атрибуты для хранения данных.
Работать с CSS-классами через JavaScript.

1. Работа со стилями элементов
   Установка стилей:
   Чтобы задать стиль элементу через JavaScript, мы используем свойство .style.

Например:
const message = document.createElement("div");
message.textContent = "Привет!";
document.body.append(message); // Добавляем элемент в DOM

// Устанавливаем стили
message.style.backgroundColor = "blue"; // Цвет фона
message.style.color = "white"; // Цвет текста
message.style.padding = "10px"; // Внутренние отступы

💡 Важно:
Имена CSS-свойств, содержащие дефисы (например, background-color), преобразуются в camelCase (backgroundColor).
Значения стилей (например, размеры) должны быть указаны с единицами измерения: px, %, em и т. д.

Чтение стилей:
Если стиль был установлен через .style, вы можете его прочитать:
console.log(message.style.backgroundColor); // "blue"

Однако, если стиль задан через CSS-файл или style в HTML, то .style его не покажет.

Пример:
/_ CSS-файл _/
.message {
border: 1px solid red;
}

javascript
console.log(message.style.border); // Пусто, так как border задан в CSS

Чтобы получить все применяемые стили (включая те, что заданы через CSS), используйте getComputedStyle:
const styles = getComputedStyle(message);
console.log(styles.border); // "1px solid red"

Динамическое изменение стилей:
Пример: увеличим высоту элемента на 40 пикселей.

Шаг 1: Получим текущую высоту элемента
const height = getComputedStyle(message).height; // Например, "50px"
console.log(height);

Шаг 2: Уберем "px" из строки и прибавим 40
const newHeight = parseFloat(height) + 40 + "px"; // "90px"

Шаг 3: Применим новое значение
message.style.height = newHeight;
console.log(message.style.height); // "90px"

CSS-переменные (Custom Properties)
CSS-переменные — это способ задавать значения, которые можно переиспользовать.

Объявление переменной в CSS:
:root {
--primary-color: green;
}

Изменение переменной через JavaScript:
document.documentElement.style.setProperty("--primary-color", "orange");
Теперь все элементы, использующие переменную --primary-color, изменят свой стиль.

2. Работа с атрибутами
   Что такое атрибуты?
   Атрибуты — это дополнительные параметры HTML-элементов:
   <img src="logo.png" alt="Логотип">
   src — путь к изображению.
   alt — текст, который показывается, если изображение не загрузилось.

Чтение атрибутов:
С помощью JavaScript можно получить значение атрибутов:
const logo = document.querySelector("img");

// Получение стандартных атрибутов
console.log(logo.src); // Абсолютный URL
console.log(logo.alt); // "Логотип"

// Получение атрибута через getAttribute:
console.log(logo.getAttribute("src")); // Относительный путь "logo.png"

💡 Зачем использовать getAttribute?
Методы, такие как .src, возвращают абсолютные пути.
Если вам нужен оригинальный, относительный путь (как в HTML), используйте getAttribute.

Изменение атрибутов:
logo.alt = "Новый логотип"; // Изменяем текст
logo.setAttribute("data-version", "3.0"); // Добавляем новый атрибут

Data-атрибуты:
Data-атрибуты начинаются с data-:
<img src="logo.png" data-version="3.0">

Вы можете получить их через dataset:
console.log(logo.dataset.version); // "3.0"

💡 Где это полезно?
Хранение дополнительной информации для работы скриптов (например, ID, статусов).

3. Работа с CSS-классами
   Добавление, удаление и проверка классов

Для работы с классами используйте .classList:
const btn = document.querySelector("button");

// Добавить класс
btn.classList.add("active");

// Удалить класс
btn.classList.remove("active");

// Переключить класс (включить/выключить)
btn.classList.toggle("active");

// Проверить наличие класса
console.log(btn.classList.contains("active")); // true или false

Полезный пример: динамическое добавление классов
Создадим кнопку, которая переключает тему сайта:
const toggleTheme = document.querySelector(".toggle-theme");

toggleTheme.addEventListener("click", () => {
document.body.classList.toggle("dark-mode");
});

CSS:
.dark-mode {
background-color: black;
color: white;
}
Теперь при клике будет переключаться темная тема.

Избегайте использования .className:
Старый метод .className заменяет все классы элемента, что неудобно:
btn.className = "new-class"; // Стирает все другие классы
Вместо этого используйте .classList.

Итог
Мы рассмотрели:

Как управлять стилями через JavaScript.
Как читать и изменять атрибуты HTML-элементов.
Как работать с data-атрибутами.
Удобные методы для управления CSS-классами.

// ------------------------------------------------------------------------------- //

## РЕАЛИЗАЦИЯ ПЛАВНОЙ ПРОКРУТКИ

Задача: Плавный скролл к разделу страницы
Идея: Когда вы нажимаете на кнопку, страница "перемещается" (скроллит) к определенному разделу (секции).
Это полезно для создания кнопок вроде "Читать дальше" или "Вернуться наверх".

1. Выбор элементов страницы
   Первое, что нужно сделать, — это найти HTML-элементы, с которыми мы будем работать.

Например:
Кнопка, которую пользователь будет нажимать.
Секция, к которой страница должна прокрутиться.

В JavaScript мы используем метод document.querySelector для выбора элементов.
Пример: HTML-код:
<button class="button-scroll-to">Прокрутить к секции</button>

<section id="section-1">Это секция 1</section>

JavaScript-код:
const buttonScrollTo = document.querySelector('.button-scroll-to'); // Находим кнопку
const section1 = document.querySelector('#section-1'); // Находим секцию

Объяснение:
.button-scroll-to — это класс кнопки (в HTML он пишется как class="button-scroll-to").
#section-1 — это ID секции (в HTML это id="section-1").

Если вы выбрали элементы правильно, то теперь buttonScrollTo и section1
содержат ссылки на HTML-элементы, которые мы можем использовать.

2. Добавление события на кнопку
   Чтобы кнопка что-то делала, мы добавляем к ней "обработчик события".
   В данном случае, мы хотим, чтобы код выполнялся при клике на кнопку.

Пример:
buttonScrollTo.addEventListener('click', function () {
console.log('Кнопка была нажата!');
});

Объяснение:
addEventListener — метод, который "слушает" события (в данном случае событие click — клик мыши).
Когда пользователь нажимает на кнопку, запускается внутренняя функция, которая выполняет указанный код.
В примере выше, когда вы нажимаете на кнопку, в консоли появляется сообщение Кнопка была нажата!.

3. Получение координат секции
   Теперь нам нужно понять, где находится секция на странице,
   чтобы прокрутить страницу именно к этому месту.

Мы используем метод getBoundingClientRect:
чтобы узнать положение секции относительно текущего видимого окна браузера (viewport).

Пример:
const s1Coords = section1.getBoundingClientRect();
console.log(s1Coords);

Результат:
javascript
{
x: 0,
y: 300,
width: 800,
height: 400,
top: 300,
right: 800,
bottom: 700,
left: 0
}
Что означают эти свойства:

top: расстояние от верхнего края окна браузера до верхней границы секции.
left: расстояние от левого края окна браузера до левой границы секции.
width и height: размеры секции.
x и y: горизонтальное и вертикальное расстояние от верхнего левого угла окна браузера.

Пример: Если top = 300, это значит, что верхняя часть секции
находится на 300 пикселей ниже верхней границы окна браузера.

4. Определение текущей позиции прокрутки
   Чтобы корректно прокрутить страницу, нам нужно учитывать текущую позицию прокрутки.

Для этого используются:
window.pageXOffset — текущая прокрутка по горизонтали.
window.pageYOffset — текущая прокрутка по вертикали.

Пример:
console.log(`Текущая прокрутка по вертикали: ${window.pageYOffset}`);
Объяснение:
Если пользователь прокрутил страницу вниз на 500 пикселей, window.pageYOffset вернет 500.

5. Прокрутка к секции с помощью window.scrollTo
   Метод window.scrollTo позволяет прокрутить страницу до нужного места.

Пример:
window.scrollTo({
left: 0, // Горизонтальная прокрутка (по умолчанию 0)
top: s1Coords.top + window.pageYOffset, // Вертикальная прокрутка
behavior: 'smooth', // Плавная прокрутка
});

Объяснение:
left: 0 — мы не прокручиваем по горизонтали.
top: s1Coords.top + window.pageYOffset — координаты секции относительно всего документа (включая текущую прокрутку).
behavior: 'smooth' — делает прокрутку плавной.

Полный код на этом этапе:
buttonScrollTo.addEventListener('click', function () {
const s1Coords = section1.getBoundingClientRect();
window.scrollTo({
left: 0,
top: s1Coords.top + window.pageYOffset,
behavior: 'smooth',
});
});

6. Современный подход: scrollIntoView
   Метод scrollIntoView упрощает прокрутку.
   Он автоматически прокручивает страницу так,
   чтобы выбранный элемент оказался в видимой области.

Пример:
buttonScrollTo.addEventListener('click', function () {
section1.scrollIntoView({ behavior: 'smooth' });
});

Объяснение:
scrollIntoView автоматически определяет координаты секции.
behavior: 'smooth' добавляет плавность.
Этот способ проще и не требует вычислений.

7. Измерение видимой области страницы
   Иногда нужно узнать размер окна браузера (viewport). Это можно сделать так:
   console.log(`Высота окна: ${document.documentElement.clientHeight}`);
   console.log(`Ширина окна: ${document.documentElement.clientWidth}`);

Пример: Если вы измените размер окна браузера, значения высоты и ширины изменятся.

Полный пример

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Плавный скролл</title>
</head>
<body>
  <button class="button-scroll-to">Прокрутить к секции</button>
  <section id="section-1" style="margin-top: 1000px;">Секция 1</section>

  <script>
    const buttonScrollTo = document.querySelector('.button-scroll-to');
    const section1 = document.querySelector('#section-1');

    // Прокрутка с использованием scrollIntoView
    buttonScrollTo.addEventListener('click', function () {
      section1.scrollIntoView({ behavior: 'smooth' });
    });

    // Альтернативный способ с scrollTo
    /*
    buttonScrollTo.addEventListener('click', function () {
      const s1Coords = section1.getBoundingClientRect();
      window.scrollTo({
        left: 0,
        top: s1Coords.top + window.pageYOffset,
        behavior: 'smooth',
      });
    });
    */
  </script>
</body>
</html>

Давайте подробно разберем эти два пункта — текущую позицию прокрутки и метод window.scrollTo,
чтобы было понятнее, зачем они нужны и как работают.

1. Определение текущей позиции прокрутки
   Когда вы работаете со страницей, положение элементов на экране зависит от текущей прокрутки.

Например:
Если страница не прокручена, верхний левый угол элемента совпадает с верхним левым углом окна браузера.
Если страница прокручена вниз или вправо, координаты элементов нужно корректировать с учетом текущей позиции прокрутки.

window.pageXOffset и window.pageYOffset:
window.pageXOffset возвращает, насколько страница прокручена по горизонтали (вправо).
window.pageYOffset возвращает, насколько страница прокручена по вертикали (вниз).

Пример:
Представим страницу с длинным содержимым:

<div style="height: 2000px;">Большое содержимое</div>

Откройте консоль в браузере и выполните код:
console.log(`Текущая прокрутка по горизонтали: ${window.pageXOffset}`);
console.log(`Текущая прокрутка по вертикали: ${window.pageYOffset}`);

Если вы находитесь в самом верху страницы, оба значения будут 0, потому что прокрутки нет.
Если прокрутите вниз, скажем, на 300 пикселей, window.pageYOffset покажет 300.
Прокрутка вправо изменит значение window.pageXOffset.

Зачем это нужно?
Представьте, что вам нужно прокрутить страницу до определенного элемента.
Если учитывать только координаты элемента относительно окна браузера (getBoundingClientRect),
вы не получите его точного положения на странице, если страница уже прокручена.
Чтобы определить абсолютное положение элемента, нужно добавить текущую вертикальную
(или горизонтальную) прокрутку к координатам элемента.

2. Прокрутка с учетом текущей позиции: window.scrollTo
   Метод window.scrollTo позволяет прокрутить страницу до определенной позиции.

Он принимает два основных параметра:
left: координата по горизонтали (в пикселях).
top: координата по вертикали (в пикселях).

Пример:
Представим, что у вас есть кнопка и секция:
<button class="scroll-btn">Прокрутить к секции</button>

<section id="target-section" style="margin-top: 1000px;">Целевая секция</section>

И JavaScript-код:
const button = document.querySelector('.scroll-btn');
const section = document.querySelector('#target-section');

button.addEventListener('click', function () {
const sectionCoords = section.getBoundingClientRect();
console.log(sectionCoords); // Посмотреть, что возвращает getBoundingClientRect

window.scrollTo({
left: 0, // Мы не хотим скроллить по горизонтали
top: sectionCoords.top + window.pageYOffset, // Добавляем текущую вертикальную прокрутку
behavior: 'smooth', // Плавная прокрутка
});
});

Разберем по частям:

Получение координат секции:

section.getBoundingClientRect() возвращает координаты элемента относительно окна браузера
(включая расстояние от верхней границы видимой области браузера до верхней границы элемента).

Если sectionCoords.top = 300, это означает, что верхняя граница секции
находится на 300 пикселей ниже верхней границы окна браузера.

Добавление текущей прокрутки:
Чтобы получить абсолютные координаты секции (относительно всего документа, а не только окна браузера),
мы добавляем текущую вертикальную прокрутку: window.pageYOffset.

Например, если страница прокручена на 500 пикселей вниз и sectionCoords.top = 300,
то абсолютное положение секции будет 300 + 500 = 800.

Плавная прокрутка:
behavior: 'smooth' делает прокрутку визуально приятной —
страница плавно перемещается вместо мгновенного скачка.

Полный процесс:
Нажимаем кнопку.
Код вычисляет координаты секции относительно окна браузера (sectionCoords.top).
Код добавляет текущую прокрутку страницы (window.pageYOffset).
Метод window.scrollTo перемещает страницу до вычисленных координат.

Готовый пример:

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Плавная прокрутка</title>
  <style>
    body {
      height: 2000px; /* Чтобы была возможность прокрутки */
    }
    section {
      margin-top: 1000px;
      padding: 50px;
      background-color: lightblue;
    }
  </style>
</head>
<body>
  <button class="scroll-btn">Прокрутить к секции</button>
  <section id="target-section">Целевая секция</section>

  <script>
    const button = document.querySelector('.scroll-btn');
    const section = document.querySelector('#target-section');

    button.addEventListener('click', function () {
      const sectionCoords = section.getBoundingClientRect();
      console.log('Координаты секции:', sectionCoords);

      window.scrollTo({
        left: 0,
        top: sectionCoords.top + window.pageYOffset,
        behavior: 'smooth',
      });
    });
  </script>
</body>
</html>
Что произойдет:

1 - Кнопка находится в самом верху страницы.
2 - Когда вы нажмете на нее, страница плавно прокрутится к секции, находящейся на 1000 пикселей ниже.

Заключение
Теперь понятно:
window.pageYOffset помогает учесть текущую прокрутку страницы,
чтобы корректно вычислить абсолютное положение элемента.
window.scrollTo использует эти координаты, чтобы прокрутить страницу до нужного места.

Зачем мы добавляем window.pageYOffset,
когда мы уже получили координаты с помощью getBoundingClientRect() ?

ChatGPT сказал:
Отличный вопрос! Давайте разберемся, почему добавляется window.pageYOffset,
когда уже получены координаты с помощью getBoundingClientRect().

1. Что возвращает getBoundingClientRect()?
   Метод getBoundingClientRect() возвращает координаты элемента относительно вида (viewport) в браузере,
   а не относительно всего документа.
   Это важно, потому что когда страница прокручена (то есть не находится в верхней части окна),
   координаты элемента относительно видимой области могут отличаться от его позиции на всей странице.

Когда вы вызываете element.getBoundingClientRect(), вы получаете:
top — расстояние от верхней границы окна браузера до верхней границы элемента.
left — расстояние от левой границы окна до левой границы элемента.

Однако, это расстояние — относительное к окну браузера,
а не к всей странице, которая может быть прокручена вниз.

2. Почему нужно добавлять window.pageYOffset?
   Когда вы прокручиваете страницу вниз (или в сторону), элемент в документе
   перемещается относительно окна браузера.
   Однако, его абсолютное положение относительно всей страницы (не только видимой области) меняется.
   Это особенно важно, когда вы хотите прокрутить страницу точно к элементу,
   а не просто к видимой части его координат.

Вот что происходит:
getBoundingClientRect().top дает расстояние от видимой области страницы до элемента,
но не учитывает текущую прокрутку страницы.

window.pageYOffset возвращает, насколько страница была прокручена по вертикали.
Эта информация нужна для того, чтобы учесть прокрутку страницы и правильно вычислить
абсолютное положение элемента на странице.

Пример:
Предположим, у вас есть элемент, который находится на 1500 пикселей ниже верхней границы страницы,
и вы прокрутили страницу на 500 пикселей вниз.

Если вы вызовете element.getBoundingClientRect(), то element.getBoundingClientRect().top
может вернуть значение, скажем, 100 пикселей
(например, элемент находится 100 пикселей ниже текущей видимой области окна).

Однако, фактически его положение относительно всей страницы будет 1500 пикселей
(начальная позиция) + 100 пикселей
(сейчас элемент в пределах видимой области) = 1600 пикселей от верхней границы страницы.

Чтобы прокрутить страницу именно в это положение, вы должны добавить
текущую прокрутку window.pageYOffset к координате, полученной с помощью getBoundingClientRect(),
чтобы корректно посчитать абсолютную позицию элемента на странице.

3. Пример с пояснениями
   Предположим, есть страница, прокрученная на 500 пикселей вниз.
   Элемент на странице имеет координаты top = 100 (в пределах видимой области).
   Но абсолютная позиция этого элемента на странице будет 100 + 500 = 600.

Вот код:
const section = document.querySelector('#target-section');
const sectionCoords = section.getBoundingClientRect(); // Получаем координаты элемента относительно окна
console.log(sectionCoords.top); // Например, 100 (элемент находится на 100 пикселей ниже верхней границы окна)

const scrollPosition = sectionCoords.top + window.pageYOffset; // Добавляем текущую прокрутку страницы
console.log(scrollPosition); // Это будет 600, если страница прокручена на 500 пикселей

window.scrollTo({
top: scrollPosition, // Прокрутка страницы до точного положения элемента
behavior: 'smooth', // Плавная прокрутка
});

4. В чем разница?
   Без window.pageYOffset:
   Вы прокрутите страницу только до того места, которое видно в окне браузера
   (например, 100 пикселей от верхней границы видимой области).

С window.pageYOffset:
Вы прокрутите страницу к правильному месту относительно всей страницы, не только видимой области.
Это важно для точной прокрутки.

5. Пример без прокрутки страницы:
   Если страница не прокручена (то есть window.pageYOffset равно 0),
   то результат будет одинаковым, как если бы вы использовали только координаты от getBoundingClientRect():

javascript:
const section = document.querySelector('#target-section');
const sectionCoords = section.getBoundingClientRect(); // Например, 100

// Так как текущая прокрутка = 0, то добавление ничего не меняет
const scrollPosition = sectionCoords.top + window.pageYOffset; // 100 + 0 = 100

window.scrollTo({
top: scrollPosition, // Прокрутка к 100 пикселям
behavior: 'smooth',
});

Заключение:
getBoundingClientRect() дает координаты относительно окна браузера.
window.pageYOffset помогает скорректировать эти координаты,
добавляя текущую прокрутку страницы, чтобы вы могли точно прокрутить страницу к нужному элементу.
Это необходимо для правильного вычисления абсолютных координат
элемента на странице, особенно когда страница прокручена.

// ------------------------------------------------------------------------------- //

## ТИПЫ СОБЫТИЙ И ОБРАБОТЧИКИ СОБЫТИЙ

1. Что такое событие (event)?
   Событие в JavaScript — это сигнал, который сообщает, что что-то произошло на веб-странице.

Например:
Пользователь щелкнул мышью.
Пользователь передвинул мышь.
Открылся полноэкранный режим.
Страница была прокручена.

Событие срабатывает независимо от того, "слушаем" мы его или нет.
Но мы можем "слушать" события с помощью обработчиков событий
(event listeners) и выполнять определенные действия.

Пример:
Вы хотите, чтобы при клике на кнопку появилась надпись:

html
<button id="myButton">Нажми меня</button>

<script>
  const button = document.getElementById('myButton');
  button.addEventListener('click', () => {
    alert('Кнопка нажата!');
  });
</script>

Когда вы нажимаете кнопку, возникает событие click.
Обработчик событий слушает это событие и выполняет заданное действие (показывает alert).

2. Различные события:
   MouseEnter
   Автор приводит пример с событием mouseenter, которое срабатывает,
   когда курсор мыши входит в элемент.
   Это похоже на CSS-событие hover.

Пример:
Допустим, у нас есть заголовок, и мы хотим показывать сообщение,
когда пользователь наводит мышь на этот заголовок:

html

<h1 id="heading">Наведи мышь сюда</h1>
<script>
  const heading = document.getElementById('heading');
  heading.addEventListener('mouseenter', () => {
    alert('Вы навели мышь на заголовок!');
  });
</script>

Когда вы подводите мышь к заголовку:
Событие mouseenter срабатывает.
Вызывается функция, которая показывает сообщение.

3. Где найти список событий?
   Автор упоминает MDN Web Docs, где есть полный список событий:

Mouse Events (мышь): click, mouseenter, mouseleave и др.
Keyboard Events (клавиатура): keydown, keyup.
Clipboard Events (буфер обмена): copy, paste.
Page Events (страница): scroll, resize.

Пример:
Если вы хотите реагировать на нажатие клавиши:

html
<input id="input" placeholder="Нажмите клавишу">

<script>
  const input = document.getElementById('input');
  input.addEventListener('keydown', (event) => {
    console.log(`Вы нажали: ${event.key}`);
  });
</script>

Когда вы нажимаете клавишу:
Срабатывает событие keydown.
В консоли отображается нажатая клавиша.

4. Способы добавления обработчиков событий
   Есть три способа добавления обработчиков событий.

4.1. addEventListener
Это современный способ добавления обработчиков.
Мы используем метод addEventListener и указываем тип события и функцию-обработчик.

Пример:
<button id="button">Кликни меня</button>

<script>
  const button = document.getElementById('button');
  button.addEventListener('click', () => {
    alert('Кнопка нажата!');
  });
</script>

Почему лучше использовать addEventListener?
Можно добавить несколько обработчиков для одного события:

javascript:
button.addEventListener('click', () => alert('Первый обработчик!'));
button.addEventListener('click', () => alert('Второй обработчик!'));
При клике на кнопку выполняются оба обработчика.

Можно удалить обработчик:
javascript:
function showAlert() {
alert('Кнопка нажата!');
}
button.addEventListener('click', showAlert);
button.removeEventListener('click', showAlert); // Удаляем обработчик

4.2. on<Event> свойства
Это старый способ, при котором обработчик привязывается к свойству элемента.

Пример:
html
Копировать код
<button id="button">Кликни меня</button>

<script>
  const button = document.getElementById('button');
  button.onclick = () => alert('Старый метод');
</script>

Недостатки:
Нельзя привязать несколько обработчиков — новый перезапишет старый.
Это устаревший метод.

5. Удаление обработчиков событий
   Иногда нужно удалить обработчик события, чтобы предотвратить повторное выполнение.

Пример:
Добавим событие mouseenter для заголовка, которое удаляется после первого срабатывания:

html

<h1 id="heading">Наведи мышь сюда</h1>
<script>
  const heading = document.getElementById('heading');
  function handleMouseEnter() {
    alert('Мышь наведена, обработчик удален!');
    heading.removeEventListener('mouseenter', handleMouseEnter);
  }
  heading.addEventListener('mouseenter', handleMouseEnter);
</script>

Наведите мышь на заголовок.
Событие mouseenter срабатывает.
Обработчик удаляется, и повторное наведение больше не вызывает сообщение.

6. Устаревший способ: атрибуты HTML
   Автор упоминает атрибуты, такие как onclick, которые можно использовать прямо в HTML.

Пример:
html
<button onclick="alert('Это из HTML')">Кликни меня</button>

Недостатки:
Код мешается с HTML.
Трудно поддерживать и читать.

7. Использование событий в разных ситуациях
   Обработка событий полезна в разных случаях:

Наведение мыши:
element.addEventListener('mouseover', () => console.log('Мышь над элементом'));

Нажатие клавиш:
document.addEventListener('keydown', (event) => console.log(event.key));

Прокрутка страницы:
window.addEventListener('scroll', () => console.log('Страница прокручена'));

Заключение:
Обработка событий — ключевая часть работы с JavaScript в браузере.

Вы узнали:
Что такое события и как их слушать.
Различные типы событий (мышь, клавиатура, прокрутка).
Как добавлять и удалять обработчики.
Разные способы написания обработчиков и их преимущества.

// ------------------------------------------------------------------------------- //

## ЧТО ТАКОЕ ФАЗЫ СОБЫТИЙ В JAVASCRIPT ?

Давайте разберем концепцию фаз событий в JavaScript максимально подробно и с примерами,
чтобы даже новичок смог ее понять.
Мы будем добавлять свои пояснения и дополнительные примеры к каждому пункту.

1. Что такое фазы событий в JavaScript?
   Когда событие, например, клик, происходит на странице,
   оно не сразу обрабатывается целевым элементом.

Событие проходит через несколько фаз:

Фаза захвата (capturing phase):
Событие начинает свой путь с корня документа (document)
и спускается по дереву DOM через всех предков целевого элемента.

Целевая фаза (target phase):
Событие достигает целевого элемента (того, на котором произошло действие, например, клик).

Фаза всплытия (bubbling phase):
После обработки на целевом элементе событие поднимается
обратно вверх через всех его предков, пока не достигнет корня.

2. Что такое DOM-дерево?
   Чтобы понять, как событие распространяется, важно знать структуру DOM (Document Object Model).
   Веб-страница организована как дерево элементов.

Например:

<!DOCTYPE html>
<html>
  <body>
    <section>
      <p>
        <a href="#">Кликни на меня</a>
      </p>
    </section>
  </body>
</html>
Это дерево можно представить так:

css
Копировать код
html
└── body
└── section
└── p
└── a (ссылка, на которую мы кликаем)

Когда вы кликаете на элемент <a>, событие проходит через все предки:
html → 2. body → 3. section → 4. p → 5. a (цель).
Затем оно всплывает обратно:
a → 4. p → 3. section → 2. body → 1. html.

3. Пример фаз событий
   Давайте создадим пример, чтобы увидеть, как событие распространяется.

HTML:

<html>
  <body>
    <section>
      <p>
        <a href="#">Кликни на меня</a>
      </p>
    </section>
  </body>
</html>

JavaScript:
// Обработчики на каждом элементе
document.querySelector('html').addEventListener('click', () => {
console.log('HTML');
}, true); // true - обработчик срабатывает на фазе захвата

document.querySelector('body').addEventListener('click', () => {
console.log('BODY');
});

document.querySelector('section').addEventListener('click', () => {
console.log('SECTION');
});

document.querySelector('p').addEventListener('click', () => {
console.log('P');
});

document.querySelector('a').addEventListener('click', () => {
console.log('A (Target)');
});

Что происходит при клике на <a>:
На фазе захвата (true):
Сначала срабатывает обработчик на html, так как событие идет сверху вниз.

На целевой фазе:
Срабатывает обработчик на <a>.

На фазе всплытия:
Обработчики срабатывают в обратном порядке: p → section → body.

В консоли вы увидите:
HTML (захват)
A (Target)
P
SECTION
BODY

4. Почему это важно?
   Фазы событий позволяют управлять поведением на разных уровнях DOM.

Например:
Управление поведением родителей и детей:
Вы можете обрабатывать клики на родительских элементах,
не добавляя обработчики к каждому дочернему элементу.

Пример:
javascript
document.querySelector('section').addEventListener('click', () => {
console.log('Клик внутри секции');
});
Теперь, кликая на <a> или <p>, вы все равно увидите сообщение: "Клик внутри секции".

Предотвращение всплытия:
Иногда нужно остановить всплытие, чтобы событие не дошло до родителей.
Пример:
document.querySelector('a').addEventListener('click', (event) => {
console.log('Клик только по ссылке');
event.stopPropagation(); // Остановить всплытие
});
Теперь клики на <a> не будут обрабатываться на уровне <p>, <section>, и т.д.

5. Как слушать события на фазе захвата?
   По умолчанию обработчики слушают события на фазе всплытия.
   Чтобы слушать их на фазе захвата, нужно передать третий аргумент true в метод addEventListener.

Пример:
document.querySelector('section').addEventListener('click', () => {
console.log('Фаза захвата в секции');
}, true);
Теперь этот обработчик сработает, когда событие спускается к целевому элементу.

6. Когда события не всплывают?
   Некоторые события не всплывают,
   например:
   focus и blur (фокусировка на элементах формы).
   mouseenter и mouseleave (вход и выход курсора мыши).

Пример:
document.querySelector('p').addEventListener('mouseenter', () => {
console.log('Курсор над абзацем');
});
Даже если <a> внутри <p>, событие mouseenter сработает только на <p>.

7. Заключение
   Фазы событий (захват, цель, всплытие) дают большую гибкость при работе с DOM:

Захват позволяет реагировать на события раньше, чем они достигнут цели.
Всплытие позволяет обрабатывать события на родительских элементах.
Управление всплытием дает контроль над тем, какие обработчики срабатывают.

Резюме:
Событие начинается с корня (html) → захват.
Доходит до целевого элемента → цель.
Возвращается вверх → всплытие.

Понимание этих фаз важно для создания сложных интерфейсов,
где события можно обрабатывать на любом уровне DOM.
Экспериментируйте с примерами и наблюдайте за порядком срабатывания событий!

// ------------------------------------------------------------------------------- //

## ФАЗЫ СОБЫТИЙ (ПРАКТИКА)

1. Что такое событие в JavaScript?
   Когда вы взаимодействуете с веб-страницей (нажимаете кнопку, вводите текст, прокручиваете страницу и т.д.),
   браузер создает событие.
   События позволяют "сообщать" JavaScript, что что-то произошло.

Пример:
<button id="myButton">Нажми меня</button>

<script>
  const button = document.getElementById('myButton');
  button.addEventListener('click', function () {
    alert('Кнопка была нажата!');
  });
</script>

Логика работы:
Мы нашли кнопку с id="myButton".
Добавили обработчик события click с помощью addEventListener.
Когда пользователь нажимает на кнопку, выполняется функция, которая выводит сообщение.

2. Что такое фазы событий?
   Когда вы кликаете на элемент, например, на ссылку, событие проходит через три фазы:

Фаза захвата (Capturing):
Событие начинает свое "путешествие" с корня документа (document)
и спускается вниз по DOM-дереву к целевому элементу.

Целевая фаза (Target):
Событие достигает элемента, на котором произошло действие.

Фаза всплытия (Bubbling):
Событие "всплывает" обратно вверх по DOM-дереву от целевого элемента к корню (document).

Визуализация:
Представьте, что вы кликаете на ссылку внутри блока <div>:

<body>
  <div>
    <a href="#">Кликни меня</a>
  </div>
</body>

Событие пройдет такие этапы:
body → div → a (захват).
a (целевая фаза).
a → div → body (всплытие).

3. Всплытие событий (Event Bubbling)
Пример:
<div class="parent">
  <button class="child">Нажми меня</button>
</div>
<script>
  // Обработчик на кнопке
  document.querySelector('.child').addEventListener('click', function () {
    alert('Кнопка нажата!');
  });

// Обработчик на родительском элементе
document.querySelector('.parent').addEventListener('click', function () {
alert('Родительский элемент обработал клик!');
});
</script>

Что происходит?
Когда вы нажимаете на кнопку .child, сначала срабатывает обработчик кнопки.
Затем событие "всплывает" и доходит до .parent, где срабатывает второй обработчик.
Почему это работает? Событие проходит через фазу всплытия.
После обработки кнопкой, оно доходит до .parent.

4. Как узнать, где произошло событие?
   JavaScript предоставляет объект event, содержащий информацию о событии.

Например:
event.target: элемент, на котором событие началось.
event.currentTarget: элемент, на котором висит обработчик.

Пример:

<div class="parent">
  <button class="child">Нажми меня</button>
</div>
<script>
  document.querySelector('.parent').addEventListener('click', function (event) {
    console.log('Где произошло событие:', event.target); // Показывает, где был клик
    console.log('На каком элементе обработчик:', event.currentTarget); // Показывает элемент с обработчиком
  });
</script>
Если вы нажмете на кнопку, консоль покажет:
Где произошло событие: <button class="child">Нажми меня</button>
На каком элементе обработчик: <div class="parent">

5. Как остановить всплытие?
   Иногда вы не хотите, чтобы событие поднималось вверх по DOM-дереву.
   Для этого используется метод stopPropagation().

Пример:

<div class="parent">
  <button class="child">Нажми меня</button>
</div>
<script>
  document.querySelector('.child').addEventListener('click', function (event) {
    event.stopPropagation(); // Останавливаем всплытие
    alert('Клик обработан только кнопкой!');
  });

document.querySelector('.parent').addEventListener('click', function () {
alert('Этот код не выполнится!');
});
</script>
Что происходит?
Клик обрабатывается только кнопкой. Родительский элемент не получит событие.

6. Фаза захвата
   По умолчанию обработчики работают на фазе всплытия.
   Но вы можете обработать событие на фазе захвата, передав третий аргумент true в addEventListener.

Пример:

<div class="parent">
  <button class="child">Нажми меня</button>
</div>
<script>
  // Захват
  document.querySelector('.parent').addEventListener(
    'click',
    function () {
      alert('Сработало на фазе захвата!');
    },
    true // Захват
  );

// Всплытие
document.querySelector('.child').addEventListener('click', function () {
alert('Сработало на фазе всплытия!');
});
</script>
Что происходит?
Если вы нажимаете на кнопку, сначала срабатывает обработчик захвата (parent), потому что он срабатывает раньше.
Затем срабатывает обработчик кнопки на фазе всплытия.

7. Зачем это нужно?
   Пример делегирования событий:
   Вместо добавления обработчиков к каждому дочернему элементу,
   можно обработать события на общем родительском элементе.
   Это упрощает код и улучшает производительность.

html

<ul class="menu">
  <li>Элемент 1</li>
  <li>Элемент 2</li>
  <li>Элемент 3</li>
</ul>
<script>
  // Обработчик на родителе
  document.querySelector('.menu').addEventListener('click', function (event) {
    if (event.target.tagName === 'LI') {
      alert(`Вы нажали на: ${event.target.textContent}`);
    }
  });
</script>
Что происходит?
Вы нажимаете на любой <li>, а обработчик родителя .menu определяет, какой элемент был нажат.

8. Итог
   Событие проходит через три фазы: захват, целевая фаза и всплытие.
   Вы можете обработать событие на любой фазе, управляя его поведением (stopPropagation()).
   event.target показывает, где событие началось, а event.currentTarget — где обработчик.
   Делегирование событий позволяет обрабатывать много дочерних элементов с помощью одного обработчика.

Этот пример кода работает на фазе всплытия.
По умолчанию, метод addEventListener добавляет обработчики событий именно на фазе всплытия,
если не указан третий аргумент.
В данном примере обработчик на элементе .menu ждет, когда событие (например, клик)
пройдет через целевой <li> и начнет "всплывать" вверх по DOM-дереву,
пока не дойдет до родительского элемента .menu.

Детальный разбор:

Что происходит?

Когда вы кликаете на один из <li>, событие сначала проходит через фазу захвата (от корня документа к <li>).
Затем достигает <li> (целевая фаза).
После этого начинается всплытие события, и обработчик на родителе .menu срабатывает.

Почему родитель .menu обрабатывает событие?
В процессе всплытия событие "проходит" через все элементы, от целевого элемента вверх по DOM-дереву.
Поскольку .menu является родителем <li>, его обработчик получает событие.

Как узнать, на каком <li> произошел клик?
Используется event.target, чтобы определить исходный элемент (тот, на котором произошло событие).
В этом примере проверяется, является ли event.target тегом LI:

javascript:
if (event.target.tagName === 'LI') {
alert(`Вы нажали на: ${event.target.textContent}`);
}

Зачем использовать делегирование событий?
Экономия ресурсов: Вместо добавления обработчика события для каждого <li>
(например, addEventListener на каждый элемент), мы добавляем его только на .menu.
Гибкость: Если динамически добавляются новые <li>, обработчик на .menu будет работать и для них.
Не нужно заново добавлять обработчики на новые элементы.

Если сделать так, чтобы обработчик сработал на фазе захвата.
Для работы на фазе захвата нужно указать третий аргумент true в методе addEventListener:

javascript:
document.querySelector('.menu').addEventListener(
'click',
function (event) {
if (event.target.tagName === 'LI') {
alert(`Вы нажали на: ${event.target.textContent}`);
}
},
true // Включаем фазу захвата
);
В этом случае обработчик на .menu сработает до того, как событие достигнет <li>.

Основное различие между фазой захвата и фазой всплытия:
Фаза захвата: Событие обрабатывается на пути от корня документа к целевому элементу.
Фаза всплытия (по умолчанию): Событие обрабатывается, когда оно движется от целевого элемента вверх по DOM-дереву.
Пример выше (без указания true) работает на фазе всплытия, что является стандартным поведением.

// ------------------------------------------------------------------------------- //

## ДЕЛЕГИРОВАНИЕ СОБЫТИЙ

Цель задачи:
У нас есть навигационные ссылки на странице, которые ведут к разным разделам страницы.
Когда мы кликаем на такую ссылку, браузер по умолчанию сразу "прыгает" к нужному разделу,
что выглядит как мгновенный переход.
Мы же хотим, чтобы этот переход был плавным, то есть,
чтобы страница постепенно прокручивалась к нужному разделу.

Как это работает?
Чтобы сделать прокрутку плавной и управлять событиями на клики, автор использует два подхода:

Первоначальный подход — добавление обработчика событий для каждой ссылки.
Оптимизированный подход — использование делегирования событий, что гораздо более эффективно.
Мы начнем с базового и простого подхода, а затем перейдем к оптимизированному решению.

Шаг 1: Без делегирования событий (простой подход)
1.1. Выбираем все ссылки
Сначала нам нужно выбрать все элементы на странице, которые являются ссылками.
В данном случае это ссылки навигации (с классом nav-link).
javascript:
const links = document.querySelectorAll('.nav-link');
document.querySelectorAll('.nav-link') выбирает все элементы на странице,
которые имеют класс nav-link. Это может быть несколько ссылок.

В результате мы получаем NodeList (это что-то вроде массива),
который содержит все найденные ссылки.

1.2. Добавляем обработчик события для каждой ссылки
Мы можем добавить обработчик события для каждой ссылки по отдельности.
Для этого используем метод .forEach(), чтобы пройти по всем ссылкам и добавить обработчик события click.

javascript:
links.forEach(link => {
link.addEventListener('click', function(event) {
event.preventDefault(); // Отменяем стандартное поведение перехода по ссылке
console.log(link); // Выводим в консоль текущую ссылку
});
});
.forEach(link => {...}) — это метод для перебора всех ссылок.
Для каждой ссылки мы добавляем обработчик клика.
Внутри обработчика мы используем event.preventDefault(),
чтобы отменить стандартное поведение браузера (т.е. чтобы он не переходил по ссылке сразу).
Теперь, при клике на любую ссылку, в консоль будет выводиться эта ссылка,
а стандартное поведение (переход по ссылке) отменяется.

1.3. Получаем ID целевого элемента
В каждой ссылке указано, куда нужно прокрутить страницу, с помощью атрибута href.

Например:
<a href="#section1" class="nav-link">Section 1</a>
Здесь атрибут href указывает на элемент с ID section1.
Мы будем использовать это значение, чтобы прокрутить страницу к соответствующему элементу.

Чтобы извлечь ID целевого элемента, мы делаем так:
const targetId = link.getAttribute('href').substring(1);

link.getAttribute('href') — получаем значение атрибута href, например #section1.
.substring(1) — обрезаем символ # в начале строки, чтобы осталась только часть section1.

1.4. Плавная прокрутка
Теперь, когда мы знаем, к какому элементу нужно прокрутить страницу (ID элемента),
мы используем метод scrollIntoView() для плавной прокрутки.

javascript:
const targetElement = document.getElementById(targetId); // Ищем элемент по ID
targetElement.scrollIntoView({ behavior: 'smooth' }); // Плавно прокручиваем к этому элементу

document.getElementById(targetId) — находим элемент с нужным ID (например, section1).
scrollIntoView({ behavior: 'smooth' }) — прокручиваем страницу к этому элементу с плавной анимацией.
Теперь, при клике на ссылку, страница плавно прокручивается к соответствующему разделу.

Шаг 2: Проблемы с этим подходом
Представь, что у нас на странице не 3 ссылки, а 1000.
Если мы будем добавлять обработчик события для каждой из них,
то это замедлит работу страницы, потому что для каждого элемента
будет создан свой обработчик события.
Это не очень эффективно.

Шаг 3: Использование делегирования событий
Чтобы решить эту проблему, автор использует подход, называемый делегированием событий.
Вместо того, чтобы добавлять обработчик для каждой ссылки,
мы добавляем один обработчик на родительский элемент,
который "слушает" все клики на своих дочерних элементах.

3.1. Что такое делегирование событий?
Делегирование событий — это способ обработки событий, когда один обработчик события
добавляется на родительский элемент, а не на каждый отдельный дочерний элемент.
Когда событие происходит (например, клик на ссылке), оно "всплывает" вверх к родителю,
и мы можем поймать это событие на родителе.

3.2. Как это работает?
Предположим, у нас есть родительский элемент, который содержит все ссылки.

Например:

<nav class="nav-links">
  <a href="#section1" class="nav-link">Section 1</a>
  <a href="#section2" class="nav-link">Section 2</a>
  <a href="#section3" class="nav-link">Section 3</a>
</nav>
Теперь мы добавляем обработчик события на родительский элемент 
(в данном случае на <nav class="nav-links">).

javascript:
const parent = document.querySelector('.nav-links');

3.3. Как поймать, на какой ссылке был клик?
Когда клик происходит, мы можем получить цель этого клика с помощью event.target.
Это свойство указывает на элемент, на котором произошло событие.

javascript:
parent.addEventListener('click', function(event) {
const target = event.target; // На каком элементе произошел клик
if (target.classList.contains('nav-link')) {
// Мы проверяем, что клик был на ссылке с классом 'nav-link'
event.preventDefault(); // Отменяем стандартное поведение
const targetId = target.getAttribute('href').substring(1);
const targetElement = document.getElementById(targetId);
targetElement.scrollIntoView({ behavior: 'smooth' });
}
});
event.target — это элемент, на котором был клик.
target.classList.contains('nav-link') — проверяем,
был ли клик на ссылке, а не на каком-то другом элементе.

Таким образом, мы добавляем один обработчик события на родителя,
и проверяем, на какой ссылке был клик, используя event.target.

3.4. Почему это эффективно?
Вместо того, чтобы добавлять обработчики на каждую ссылку,
мы добавляем один обработчик на родительский элемент.
Это делает код более эффективным и быстрым, потому что:
Мы добавляем только один обработчик.
Мы не создаем дублирующие функции, которые будут занимать память и ресурсы.

Итог
Первоначальный способ (без делегирования событий) — для каждой ссылки добавляется свой обработчик,
что становится неэффективно, если элементов много.
Делегирование событий — добавляется один обработчик на родительский элемент,
который проверяет, на каком именно дочернем элементе произошло событие.
Это более эффективно, особенно когда количество элементов большое.
Этот подход делает код чище и проще для поддержки,
а также улучшает производительность страницы.

// ------------------------------------------------------------------------------- //

## DOM ПЕРЕМЕЩЕНИЕ

Разбор лекции: Путешествие по DOM (DOM Traversing)
В этой лекции рассказывается, как "ходить" по DOM-дереву (Document Object Model).
Это важно, потому что иногда нам нужно выбрать элемент относительно другого элемента,
не зная заранее точную структуру страницы.

Что такое DOM Traversing (путешествие по DOM)?
DOM (Document Object Model) — это структура HTML-документа, представляемая в виде дерева.
Каждый узел (node) в этом дереве может быть:

Элементом (например, <div>, <span>).
Текстом (например, текст внутри элемента).
Комментариями (<!-- comment -->).

Traversing означает "путешествие" по этому дереву, включая:
Переход вниз к дочерним элементам.
Переход вверх к родителям.
Переход вбок к соседям.

Примерная структура страницы
Пример HTML для демонстрации:

<header class="header-title">
  <h1 id="main-title">
    Welcome! <span class="highlight">Hello</span>
    <!-- This is a comment -->
    <br>
    <span class="highlight">World</span>
  </h1>
  <h4>Subtitle</h4>
</header>
Мы будем использовать h1 (id="main-title") как начальную точку и перемещаться по дереву.

1. Переход вниз (дочерние элементы)
   1.1. Использование querySelector и querySelectorAll
   Эти методы позволяют находить элементы внутри других элементов.

const h1 = document.getElementById('main-title');

// Найти все элементы с классом "highlight" внутри H1
const highlights = h1.querySelectorAll('.highlight');
console.log(highlights); // NodeList (псевдо-массив) из двух <span>

Пояснение:
querySelectorAll находит всех потомков элемента, независимо от уровня вложенности.
В примере, мы нашли <span> с классом highlight, даже если они вложены глубже.

1.2. Использование childNodes
Этот метод возвращает все дочерние узлы, включая текст и комментарии.
console.log(h1.childNodes);
// Вывод:
// NodeList(5) [Text, span.highlight, Text, br, span.highlight, Text]

Пояснение:
childNodes возвращает всё, что внутри элемента: текстовые узлы, комментарии, элементы.

1.3. Использование children
Этот метод возвращает только элементы, исключая текст и комментарии.
console.log(h1.children);
// Вывод:
// HTMLCollection(3) [span.highlight, br, span.highlight]

Пояснение:
children игнорирует текст и комментарии, возвращая только элементы.
Это полезно, если вы работаете исключительно с элементами.

1.4. Первый и последний ребенок: firstElementChild, lastElementChild

javascript:
console.log(h1.firstElementChild); // <span class="highlight">Hello</span>
console.log(h1.lastElementChild); // <span class="highlight">World</span>

Пояснение:
firstElementChild возвращает первый элемент среди детей.
lastElementChild возвращает последний.

2. Переход вверх (родители)
   2.1. Использование parentNode и parentElement
   Эти методы позволяют находить родителя элемента.

javascript:
console.log(h1.parentNode); // <header class="header-title">
console.log(h1.parentElement); // <header class="header-title">

Пояснение:
Оба метода обычно возвращают одно и то же.
parentNode может вернуть не-элемент (например, Document), а parentElement — только элемент.

2.2. Использование closest
Метод closest ищет ближайшего предка, соответствующего селектору.

javascript:
const header = h1.closest('.header-title');
console.log(header); // <header class="header-title">

const sameH1 = h1.closest('h1');
console.log(sameH1); // Сам h1, т.к. он сам соответствует селектору

Пояснение:
closest ищет вверх по дереву до тех пор, пока не найдет элемент, соответствующий селектору.
Если текущий элемент соответствует селектору, он сам возвращается.

3. Переход вбок (соседи)
   3.1. previousElementSibling и nextElementSibling
   Позволяют находить предыдущего и следующего соседа.

javascript:
console.log(h1.previousElementSibling); // null (нет соседа перед h1)
console.log(h1.nextElementSibling); // <h4>Subtitle</h4>

Пояснение:
previousElementSibling возвращает предыдущий элемент-сосед.
nextElementSibling возвращает следующий элемент-сосед.

3.2. Получение всех соседей
Если нужно получить всех соседей, можно:

Перейти к родителю.
Получить всех детей родителя.
Исключить текущий элемент.

javascript:
const siblings = Array.from(h1.parentElement.children);
siblings.forEach(sibling => {
if (sibling !== h1) {
sibling.style.transform = 'scale(0.5)';
}
});

Пояснение:
Array.from преобразует HTMLCollection в массив.
Мы фильтруем текущий элемент и применяем изменения только к соседям.

Итоги:
Вниз:
querySelector, querySelectorAll — для потомков.
childNodes, children — для прямых детей.
firstElementChild, lastElementChild — для первого и последнего ребенка.

Вверх:
parentNode, parentElement — для родителей.
closest — для ближайшего предка по селектору.

Вбок:
previousElementSibling, nextElementSibling — для соседей.
Через parentElement.children можно получить всех соседей.

Эти методы позволяют эффективно работать с DOM-деревом, помогая решать сложные задачи,
такие как делегирование событий или динамическое изменение страницы.

// ------------------------------------------------------------------------------- //

## СОЗДАНИЕ КОМПОНЕНТА С ВКЛАДКАМИ

Создание вкладочного компонента (tabs) — это популярная задача в веб-разработке,
которая помогает структурировать контент, делая его удобным для пользователей.
Давайте разберем логику работы такого компонента,
исходя из транскрипции, с пояснениями и примерами для новичков.

Что такое вкладочный компонент?
Вкладочный компонент состоит из набора вкладок и связанного с ними контента.
Когда пользователь кликает на вкладку, отображается соответствующий контент, а остальные скрываются.
Это работает аналогично вкладкам в браузере:
каждая вкладка имеет своё содержимое.

Пример:

Вкладки: "Домой", "О нас", "Контакты".
При нажатии на "О нас" отображается текст с описанием компании, а другие тексты скрываются.

Шаг 1. Структура HTML
Создадим базовую HTML-разметку:

<section class="operations">
  <div class="operations__tab-container">
    <button class="operations__tab operations__tab--1" data-tab="1">Вкладка 1</button>
    <button class="operations__tab operations__tab--2" data-tab="2">Вкладка 2</button>
    <button class="operations__tab operations__tab--3" data-tab="3">Вкладка 3</button>
  </div>

  <div class="operations__content operations__content--1 operations__content--active">
    <p>Содержимое вкладки 1</p>
  </div>
  <div class="operations__content operations__content--2">
    <p>Содержимое вкладки 2</p>
  </div>
  <div class="operations__content operations__content--3">
    <p>Содержимое вкладки 3</p>
  </div>
</section>

Разбор HTML:
operations\_\_tab-container — контейнер для кнопок вкладок.

Кнопки вкладок (operations\_\_tab):
Каждая кнопка имеет атрибут data-tab, который указывает на связанное содержимое.

Контент вкладок (operations**content):
У каждой вкладки свой класс, например operations**content--1.

Класс operations\_\_content--active определяет, какая вкладка видна.

Шаг 2. CSS для вкладок
Чтобы вкладки переключались, нам нужно менять стили. Пример CSS:

css
Копировать код
.operations**content {
display: none;
}
.operations**content--active {
display: block;
}
.operations**tab {
cursor: pointer;
}
.operations**tab--active {
font-weight: bold;
border-bottom: 2px solid black;
}

Скрытие содержимого: Все элементы с классом operations**content изначально скрыты (display: none).
Активное содержимое: Класс operations**content--active делает вкладку видимой (display: block).
Активная вкладка: operations\_\_tab--active выделяет нажатую кнопку (например, делает её жирной).

Шаг 3. JavaScript для функциональности

1. Выбор элементов
   Сначала нужно выбрать элементы из DOM (Document Object Model):

const tabs = document.querySelectorAll('.operations**tab'); // Все кнопки вкладок
const tabsContainer = document.querySelector('.operations**tab-container'); // Контейнер вкладок
const tabsContent = document.querySelectorAll('.operations\_\_content'); // Все содержимые

2. Добавление события клика
   Мы будем использовать делегирование событий.
   Это значит, что обработчик клика добавляется на общий контейнер, а не на каждую кнопку.

javascript:
tabsContainer.addEventListener('click', function (e) {
const clicked = e.target.closest('.operations\_\_tab'); // Найти ближайшую кнопку
if (!clicked) return; // Если кликнули мимо кнопок, завершить функцию

// Удалить активные классы
tabs.forEach(tab => tab.classList.remove('operations**tab--active'));
tabsContent.forEach(content => content.classList.remove('operations**content--active'));

// Добавить активные классы
clicked.classList.add('operations**tab--active');
document.querySelector(`.operations**content--${clicked.dataset.tab}`).classList.add('operations\_\_content--active');
});

Разбор кода:

closest():
Ищет ближайший родительский элемент с указанным классом.
Это полезно, если внутри кнопки есть текст или иконки.

Проверка на клик мимо вкладок:
Если клик произошёл не на кнопке, clicked будет null, и мы выходим из функции.

Сброс классов:
Перед активацией новой вкладки мы убираем классы у всех вкладок и контента.

Активация:
Добавляем класс operations\_\_tab--active к нажатой кнопке.
Показ соответствующего контента с помощью data-tab.

Полный код JavaScript:

const tabs = document.querySelectorAll('.operations**tab');
const tabsContainer = document.querySelector('.operations**tab-container');
const tabsContent = document.querySelectorAll('.operations\_\_content');

tabsContainer.addEventListener('click', function (e) {
const clicked = e.target.closest('.operations\_\_tab');
if (!clicked) return;

// Удалить текущие активные классы
tabs.forEach(tab => tab.classList.remove('operations**tab--active'));
tabsContent.forEach(content => content.classList.remove('operations**content--active'));

// Добавить активный класс нажатой вкладке
clicked.classList.add('operations\_\_tab--active');

// Показать соответствующий контент
document.querySelector(`.operations__content--${clicked.dataset.tab}`).classList.add('operations\_\_content--active');
});

Пример работы
Вы видите три вкладки.
При клике на вкладку:
Нажатая кнопка становится активной.
Отображается связанное содержимое.

Почему в этом коде используется closest('.operations\_\_tab') ?
Ведь кнопка .operations.tab не родитель а наоборот дочерний элемент для tabsContainer.

ChatGPT сказал:
Давайте разберёмся, почему используется метод closest('.operations**tab') в контексте этого кода,
несмотря на то, что .operations**tab — это дочерний элемент для tabsContainer, а не родительский.

Почему именно closest?
Вот ключевой момент:
closest не обязательно должен находить родителя.
Он также проверяет сам элемент, на котором вызван метод.
В данном случае, цель closest('.operations**tab') — убедиться,
что клик произошёл на кнопке .operations**tab
или на её внутреннем элементе (например, дочернем span),
а затем вернуть саму кнопку .operations\_\_tab.

// ------------------------------------------------------------------------------- //

## ПЕРЕДАЧА АРГУМЕНТОВ ОБРАБОТЧИКАМ СОБЫТИЙ

Давайте разберем эту транскрибацию с подробными пояснениями и примерами, чтобы было понятно даже новичку.
Автор рассказывает о том, как создать эффект на странице, где при наведении на одну из ссылок навигации
остальные элементы (включая логотип) становятся менее заметными,
а при уходе мыши всё возвращается в нормальное состояние.
При этом он демонстрирует, как передавать значения в функции-обработчики событий.

Ключевые моменты, которые рассматривает автор:
Использование делегирования событий.
Различие между mouseover и mouseenter.
Выбор элементов через DOM и работа с их свойствами.
Как передать значения в обработчик событий.
Рефакторинг кода с использованием bind для повышения читаемости.

Шаг 1: Цель эффекта и структура HTML
Эффект: при наведении на одну из ссылок навигации:
Сама ссылка остаётся видимой.
Остальные элементы, включая ссылки и логотип, становятся менее заметными
(например, их прозрачность (opacity) меняется на 0.5).
При уходе мыши всё возвращается к нормальной прозрачности.

HTML-структура:

<nav class="nav">
  <ul>
    <li class="nav__item"><a href="#" class="nav__link">Home</a></li>
    <li class="nav__item"><a href="#" class="nav__link">About</a></li>
    <li class="nav__item"><a href="#" class="nav__link">Contact</a></li>
  </ul>
  <img src="logo.png" alt="Logo" class="nav__logo">
</nav>

Ссылки навигации имеют класс nav**link.
Логотип имеет класс nav**logo.

Шаг 2: Делегирование событий
Делегирование событий позволяет повесить один обработчик на общий родительский элемент
(в данном случае nav), вместо того чтобы вешать обработчики на каждую ссылку.

Почему это удобно?
Меньше кода: один обработчик вместо нескольких.
Легче поддерживать: если добавить новую ссылку, обработчик уже работает.
Используется всплытие событий: событие "всплывает" от целевого элемента вверх по DOM.

Код:
// Выбираем навигацию
const nav = document.querySelector('.nav');

// Добавляем обработчик событий
nav.addEventListener('mouseover', function (e) {
console.log(e.target); // Проверяем, на какой элемент наведена мышь
});

Шаг 3: Различие между mouseover и mouseenter
mouseover: Всплывает, поэтому событие достигает родительского элемента.
mouseenter: Не всплывает, ограничивается элементом.
В данном случае используется mouseover, так как нужно, чтобы событие дошло до родителя nav.

Шаг 4: Выбор целевого элемента
Когда пользователь наводит мышь на элемент, обработчик проверяет,
является ли этот элемент ссылкой (nav\_\_link).

Код:
nav.addEventListener('mouseover', function (e) {
if (e.target.classList.contains('nav\_\_link')) {
console.log('Навели на ссылку:', e.target);
}
});

Метод classList.contains() проверяет, есть ли у элемента определённый класс.

Шаг 5: Изменение прозрачности элементов
Чтобы остальные ссылки и логотип стали менее заметными,
нужно:
Найти всех соседей целевой ссылки.
Изменить их прозрачность.

Код:
nav.addEventListener('mouseover', function (e) {
if (e.target.classList.contains('nav\_\_link')) {
const link = e.target;

    // Ищем родителя и все дочерние элементы
    const siblings = nav.querySelectorAll('.nav__link');
    const logo = nav.querySelector('.nav__logo');

    // Меняем прозрачность соседей
    siblings.forEach(el => {
      if (el !== link) el.style.opacity = 0.5; // Остальные ссылки
    });
    logo.style.opacity = 0.5; // Логотип

}
});

// Восстановление прозрачности
nav.addEventListener('mouseout', function (e) {
if (e.target.classList.contains('nav**link')) {
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => (el.style.opacity = 1));
    logo.style.opacity = 1;

}
});

Шаг 6: Передача параметров в обработчик
Автор показывает, как передать параметр
(например, значение прозрачности) в функцию-обработчик.

Шаг 7: Рефакторинг с bind
Вместо дублирования кода можно создать универсальную функцию:

javascript:
const handleHover = function (e, opacity) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

// Используем bind для передачи параметра
nav.addEventListener('mouseover', handleHover.bind(null, 0.5));
nav.addEventListener('mouseout', handleHover.bind(null, 1));

Итог:
Делегирование событий упрощает обработку событий.
bind позволяет передавать параметры в обработчик, сохраняя читаемость кода.
Логика работы:
Наведение мыши: находим целевой элемент, изменяем прозрачность соседей.
Уход мыши: возвращаем прозрачность.
Это мощный инструмент для создания интерактивных интерфейсов.

Вы сказали:
Все равно ты не подробно разобрал транскрибацию, расскажи более подробно именно про метода bind.
Что будет если убрать параметр opacity function (e, opacity).

ChatGPT сказал:
Давайте более подробно разберём метод bind и что произойдёт,
если убрать параметр opacity из функции (e, opacity).

Что делает метод bind?
Метод bind создаёт новую функцию, которая "привязывает"
указанное значение к ключевому слову this.

Это позволяет:
Управлять значением this внутри функции.
Передавать дополнительные параметры, которые будут доступны в новой функции.

Формат:
const boundFunction = originalFunction.bind(thisArg, arg1, arg2, ...);

originalFunction — исходная функция, которую мы хотим модифицировать.
thisArg — значение, которое будет установлено для this внутри функции.
arg1, arg2, ... — дополнительные параметры, которые "запекаются" в новую функцию.

Как используется bind в обработчике событий?
В нашем примере bind позволяет передать дополнительный параметр opacity в обработчик события:

javascript:
nav.addEventListener('mouseover', handleHover.bind(null, 0.5));
nav.addEventListener('mouseout', handleHover.bind(null, 1));
handleHover.bind(null, 0.5):

Создаётся новая функция, где this внутри функции будет null (так как мы явно указали null).
Второй параметр (0.5) "запекается" в функцию.
При вызове этой функции opacity будет равно 0.5.

handleHover.bind(null, 1):
Аналогично, создаётся новая функция, где this — это null, а opacity равно 1.

Разберём функцию handleHover:
Исходный код функции:

javascript:
const handleHover = function (e, opacity) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity; // Используем переданный параметр
    });
    logo.style.opacity = opacity; // Используем переданный параметр

}
};

Что происходит здесь?
Функция принимает два аргумента:

e — объект события.
opacity — переданный с помощью bind параметр (0.5 или 1).

opacity управляет прозрачностью:
При наведении (mouseover) — прозрачность остальных элементов становится 0.5.
При уходе (mouseout) — прозрачность возвращается к 1.

Что будет, если убрать параметр opacity?
Если убрать параметр opacity из функции, она будет выглядеть так:

javascript:
const handleHover = function (e) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = 0.5; // Жёстко задано
    });
    logo.style.opacity = 0.5; // Жёстко задано

}
};

Проблемы:
Значение прозрачности (opacity) жёстко зашито в коде:
Нельзя будет изменить прозрачность для разных событий.
При уходе мыши (mouseout) прозрачность вернётся к 0.5, а не к 1.

Обработчик событий:
javascript:
nav.addEventListener('mouseover', handleHover);
nav.addEventListener('mouseout', handleHover);

Обе функции будут вызывать одинаковую логику.
Это не даёт возможности гибко управлять прозрачностью в зависимости от события.

Почему важно передавать opacity?
Передача opacity через bind делает код гибким и универсальным.
Теперь мы можем использовать одну функцию для разных значений:

Для mouseover — передаём 0.5.
Для mouseout — передаём 1.

Итоговый код:
const handleHover = function (e, opacity) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

nav.addEventListener('mouseover', handleHover.bind(null, 0.5));
nav.addEventListener('mouseout', handleHover.bind(null, 1));

Как работает bind на практике?
Пример:
function greet(greeting, name) {
console.log(`${greeting}, ${name}!`);
};

const greetHello = greet.bind(null, 'Hello');
greetHello('Alice'); // Вывод: Hello, Alice!
greetHello('Bob'); // Вывод: Hello, Bob!
greetHello создаётся с уже "запечённым" параметром greeting = 'Hello'.
Так как мы для this передали аргумент null, второй аргумент 'Hello' присвоилось для параметра greeting.
Потом вызвав функция через переменную greetHello('Alice') аргумент 'Alice' присвоилось для параметра name.
Результат: Hello, Alice!

Если opacity не передавать через bind, но использовать this
Мы могли бы переписать функцию, используя только this, без явного параметра opacity:

javascript:
const handleHover = function (e) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    const opacity = this; // `this` используется как значение прозрачности

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

// Передаём значение `this` через bind
nav.addEventListener('mouseover', handleHover.bind(0.5));
nav.addEventListener('mouseout', handleHover.bind(1));
Здесь bind(0.5) устанавливает this = 0.5.
Значение this внутри handleHover становится параметром opacity.
Этот подход также гибкий, но менее читаемый для новичков.

Вы сказали:
Я имею ввиду можно ли убрать параметр opacity и при передачи параметра
обработчикам событий к примеру 0.5 и использовать ключевое слово this внутри функции.

ChatGPT сказал:
Да, вы можете убрать параметр opacity и вместо этого использовать ключевое слово this
для передачи значения в обработчик событий.
Это возможно благодаря тому, что метод bind позволяет устанавливать значение для this.
Давайте подробно разберём, как это работает.

Переписываем функцию с использованием this
Изначальная функция выглядела так:

const handleHover = function (e, opacity) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

Теперь перепишем её, убрав параметр opacity и используя this:

const handleHover = function (e) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    // Используем this как значение прозрачности
    const opacity = this;

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

Передача this через bind:
Теперь при вызове обработчика с addEventListener мы будем использовать метод bind,
чтобы передать значение this:

nav.addEventListener('mouseover', handleHover.bind(0.5)); // this = 0.5
nav.addEventListener('mouseout', handleHover.bind(1)); // this = 1

В первом случае, когда срабатывает событие mouseover, this внутри handleHover будет равно 0.5.
Во втором случае, при событии mouseout, this будет равно 1.

Почему это работает?
Метод bind создаёт новую функцию, где:
Значение this внутри функции фиксируется на то, что вы передали в bind.
JavaScript гарантирует, что при вызове этой новой функции this будет равно указанному значению.

Пример:

function showThis() {
console.log(this);
}

const boundShowThis = showThis.bind('Hello World');
boundShowThis(); // Вывод: 'Hello World'

В обработчике событий:
Когда вызывается обработчик, браузер передаёт объект события (e) как первый параметр в функцию.
Однако значение this берётся из того, что было передано в bind.

Итоговый код:
Теперь у нас полный рабочий пример:

const handleHover = function (e) {
if (e.target.classList.contains('nav**link')) {
const link = e.target;
const siblings = nav.querySelectorAll('.nav**link');
const logo = nav.querySelector('.nav\_\_logo');

    const opacity = this; // Значение передано через bind

    siblings.forEach(el => {
      if (el !== link) el.style.opacity = opacity;
    });
    logo.style.opacity = opacity;

}
};

nav.addEventListener('mouseover', handleHover.bind(0.5)); // Уменьшить прозрачность
nav.addEventListener('mouseout', handleHover.bind(1)); // Вернуть прозрачность

Преимущества и недостатки использования this:

Преимущества:
Упрощение сигнатуры функции — меньше параметров.
Чёткое использование bind для передачи дополнительных данных.

Недостатки:
Код становится менее очевидным, особенно для новичков.
Не сразу понятно, откуда берётся this.

Если вы захотите передать дополнительные данные
(например, ещё один параметр), this уже будет занято.

Альтернативы:
Если вы хотите избежать неоднозначности с this,
можно оставить параметр opacity в функции.
Но для коротких функций, таких как в примере,
использование this через bind — элегантное и рабочее решение.

// ------------------------------------------------------------------------------- //

## РЕАЛИЗАЦИЯ ЛИПКОЙ НАВИГАЦИИ - СОБЫТИЕ ПРОКРУТКИ

Давайте подробно разберем каждую часть объяснения автора,
дополним его примерами и пояснениями,
чтобы сделать материал максимально понятным для новичков.

Что такое "Sticky Navigation"?
Sticky Navigation — это эффект, при котором меню (или любая другая панель навигации)
закрепляется в верхней части окна браузера,
как только пользователь прокручивает страницу до определённой точки.
Например, меню остаётся видимым, даже если вы продолжаете скроллить вниз.

Как работает Sticky Navigation?
HTML-структура:
Навигационная панель имеет класс sticky,
который мы будем добавлять динамически при скролле страницы.

html

<header class="nav">
    <ul>
        <li><a href="#section1">Section 1</a></li>
        <li><a href="#section2">Section 2</a></li>
        <li><a href="#section3">Section 3</a></li>
    </ul>
</header>

CSS: Мы создаём стиль для класса sticky, который фиксирует панель в верхней части страницы.

.sticky {
position: fixed;
top: 0;
width: 100%;
background-color: rgba(255, 255, 255, 0.9); /_ Полупрозрачный фон _/
z-index: 10;
}

JavaScript:
Логика для добавления или удаления класса sticky реализуется с помощью события прокрутки страницы.

Реализация через событие scroll:
Логика:
Определяем точку, в которой панель должна стать "липкой".
Добавляем обработчик события scroll для отслеживания текущей позиции прокрутки.
При достижении указанной точки добавляем класс sticky. Если прокрутка выше точки — удаляем его.

Пример кода:
// Выбираем элементы
const nav = document.querySelector('.nav'); // Панель навигации
const section1 = document.querySelector('#section1'); // Первая секция

// Определяем координаты первой секции
const initialCoords = section1.getBoundingClientRect(); // Возвращает объект с координатами элемента

// Добавляем обработчик события прокрутки
window.addEventListener('scroll', function () {
if (window.scrollY > initialCoords.top) {
nav.classList.add('sticky');
} else {
nav.classList.remove('sticky');
}
});

Объяснение кода для новичков:
getBoundingClientRect():
Метод возвращает объект с информацией о положении элемента
на странице относительно окна просмотра (viewport).

javascript:
console.log(section1.getBoundingClientRect());

Например, вы можете получить:
{
top: 500, // Расстояние от верхней границы секции до верха окна
left: 0, // Расстояние от левой границы секции до левого края окна
width: 1200, // Ширина элемента
height: 800 // Высота элемента
}

scrollY:
Свойство window.scrollY показывает, сколько пикселей прокручено
сверху относительно начального положения страницы.

javascript:
console.log(window.scrollY); // Например, 400 пикселей

Добавление и удаление классов:
В зависимости от условий добавляем или удаляем класс:

nav.classList.add('sticky'); // Добавляет класс "sticky"
nav.classList.remove('sticky'); // Убирает класс "sticky"

Почему событие scroll неэффективно?
Событие scroll срабатывает очень часто, даже при малейшем движении страницы.
Это может привести к плохой производительности, особенно на мобильных устройствах.
Решение проблемы: использовать Intersection Observer API.

Что дальше?
Автор упоминает, что scroll — это базовый метод, но он не оптимален.
Следующим шагом будет изучение Intersection Observer API,
который позволяет более эффективно отслеживать положение элементов на странице.

Дополнительный пример: Замедление скролла
Чтобы улучшить производительность, можно ограничить количество вызовов обработчика события scroll.
Например, используя метод throttling (дросселирование).

Код:
let lastScroll = 0;

window.addEventListener('scroll', () => {
const currentScroll = window.scrollY;

    // Выполняем логику только, если разница в прокрутке больше 50px
    if (Math.abs(currentScroll - lastScroll) > 50) {
        if (currentScroll > initialCoords.top) {
            nav.classList.add('sticky');
        } else {
            nav.classList.remove('sticky');
        }
        lastScroll = currentScroll;
    }

});

Заключение:
Мы реализовали базовую логику "липкой" панели навигации с помощью события scroll.
Для улучшения производительности рекомендуется изучить Intersection Observer API,
который позволяет оптимизировать такие задачи.

// ------------------------------------------------------------------------------- //

## ЛУЧШИЙ СПОСОБ - API INTERSECTION OBSERVER

Подробное объяснение Intersection Observer API для новичков с примерами.

Intersection Observer API используется для наблюдения за тем,
как элемент пересекает другой элемент или границы экрана (viewport).
Это позволяет эффективно управлять событиями, связанными с прокруткой или изменением видимости элемента.
Давайте разберем логику работы API пошагово, а затем посмотрим, как его применить на практике.

1. Основы Intersection Observer API
   Что это такое и зачем нужно?

Intersection Observer API позволяет отслеживать пересечения:

Элемента-цели (target element) с другим элементом (например, областью экрана).
Области экрана с учетом настроенных параметров (например, процент видимости).

Это полезно для таких задач, как:
Показ или скрытие элементов при прокрутке.
Реализация "липкой" (sticky) навигации.
Ленивая загрузка изображений.

2. Основные шаги использования API
   Шаг 1. Создание наблюдателя (Observer)
   Создаем объект IntersectionObserver и указываем:

Callback-функцию — что делать, когда условие пересечения выполняется.
Параметры (options) — какие именно пересечения отслеживать.

Пример:
const observer = new IntersectionObserver(callback, options);

Шаг 2. Указание элемента для наблюдения
Указываем целевой элемент, за которым хотим следить:
observer.observe(targetElement);

3. Подробное объяснение с примерами
   Пример: Базовое наблюдение
   Настраиваем параметры:

const options = {
root: null, // Наблюдаем за пересечением с экраном.
threshold: 0.1 // Срабатывает, когда 10% элемента видны.
};

root: указывает, относительно чего отслеживать пересечение. null означает, что относительно экрана.
threshold: указывает процент видимости элемента, при котором вызывается callback.
Например:
0 — когда элемент полностью выходит из поля зрения.
1 — когда элемент полностью виден.
Массив значений (например, [0, 0.5, 1]) позволяет вызывать callback на разных стадиях видимости.

Создаем функцию callback:

const callback = (entries, observer) => {
entries.forEach(entry => {
console.log(entry.isIntersecting); // true, если элемент пересекается с root.
});
};

Связываем всё вместе:
const observer = new IntersectionObserver(callback, options);
const target = document.querySelector('.section1');
observer.observe(target);

Когда 10% элемента .section1 становятся видимыми или невидимыми, callback срабатывает.

Разбор: Как это работает?
Каждый раз, когда пересечение между элементом и root достигает заданного порога (threshold),
вызывается callback.

Callback получает:
entries — массив объектов пересечения. Каждый объект содержит данные, такие как:
entry.isIntersecting: true/false — пересекается ли элемент с root.
entry.intersectionRatio: текущий процент пересечения.
entry.target: сам целевой элемент.
observer — сам объект IntersectionObserver.
Можно использовать, например, чтобы прекратить наблюдение.

4. Реализация Sticky Navigation
   Задача:
   Создать липкую навигацию, которая появляется,
   когда заголовок страницы (header) полностью выходит за пределы экрана.

Шаг 1. Выбираем целевой элемент
const header = document.querySelector('.header');

Шаг 2. Настраиваем параметры
const options = {
root: null, // Отслеживаем относительно viewport.
threshold: 0, // Срабатывает, когда элемент полностью выходит.
rootMargin: '-90px' // Учитываем высоту навигации (90px).
};

Шаг 3. Определяем callback-функцию

const stickyNav = (entries) => {
const [entry] = entries; // Берем первый элемент массива entries.
if (!entry.isIntersecting) {
document.body.classList.add('sticky'); // Добавляем класс, если header вышел.
} else {
document.body.classList.remove('sticky'); // Убираем класс, если header снова виден.
}
};

Шаг 4. Создаем наблюдатель и запускаем его
const headerObserver = new IntersectionObserver(stickyNav, options);
headerObserver.observe(header);

Теперь, когда заголовок (header) полностью выходит за пределы экрана, навигация становится "липкой".
Как только заголовок возвращается в видимость, навигация перестает быть "липкой".

5. Итог
   Intersection Observer API — мощный инструмент для работы с событиями прокрутки.

Он:
Позволяет эффективно управлять видимостью элементов.
Упрощает реализацию сложных интерфейсов, таких как sticky navigation.
Работает более производительно, чем события scroll или resize.
Рекомендуется экспериментировать с настройками threshold и rootMargin,
чтобы лучше понять, как API работает в разных сценариях.

// ------------------------------------------------------------------------------- //

## ОТОБРАЖЕНИЕ ЭЛЕМЕНТОВ НА ПРОКРУТКЕ

Подробное объяснение работы Intersection Observer API с примером и расширением для новичков.
В этом уроке рассматривается создание эффекта "появления элементов при прокрутке" на веб-странице.
Этот эффект полезен для улучшения дизайна страниц и улучшения пользовательского опыта.
Вот пошаговое объяснение и примеры, чтобы понять, как это работает.

Шаг 1: Подготовка CSS для анимации
Добавление класса section--hidden:
Этот класс будет изначально скрывать элементы на странице, делая их прозрачными и смещая их вниз.

css
.section--hidden {
opacity: 0;
transform: translateY(20px);
transition: opacity 0.3s ease, transform 0.3s ease;
}
opacity: 0; делает элемент полностью прозрачным.
transform: translateY(20px); смещает элемент вниз на 20px.
transition задает плавный переход для видимости и положения элемента, когда класс убирается.
Элементы вернутся на место и станут видимыми, если этот класс удалить.

Шаг 2: Добавление класса section--hidden с помощью JavaScript
Вместо того чтобы вручную добавлять класс section--hidden к каждому элементу в HTML,
добавляем его через JavaScript.
Это более универсальный подход, так как позволяет обрабатывать страницы, даже если JavaScript отключен.

// Находим все секции
const allSections = document.querySelectorAll('.section');

// Добавляем скрывающий класс к каждой секции
allSections.forEach(section => section.classList.add('section--hidden'));

Шаг 3: Создание Intersection Observer
Что делает Intersection Observer?
Он отслеживает, входит ли элемент в область видимости (viewport).
Это удобно для выполнения действий, например, появления элементов.

Как это работает:
Создаем новый объект IntersectionObserver, передавая ему callback-функцию и настройки (options).
Callback-функция будет вызываться каждый раз, когда наблюдаемый элемент пересекает границу видимости.

const revealSection = (entries, observer) => {
entries.forEach(entry => {

        // Проверяем, входит ли элемент в область видимости
        if (!entry.isIntersecting) return;

        // Убираем класс, чтобы сделать элемент видимым
        entry.target.classList.remove('section--hidden');

        // Прекращаем наблюдение за этим элементом
        observer.unobserve(entry.target);
    });

};

const observerOptions = {
root: null, // Область наблюдения — вся область видимости (viewport)
threshold: 0.15, // Элемент должен быть видим на 15%, чтобы сработал callback
};

const sectionObserver = new IntersectionObserver(revealSection, observerOptions);

// Подключаем Observer к каждой секции
allSections.forEach(section => sectionObserver.observe(section));

Подробное объяснение кода:
Callback-функция:

entries — массив объектов, каждый из которых описывает наблюдаемый элемент.
observer — сам объект IntersectionObserver.

javascript:
const revealSection = (entries, observer) => {
entries.forEach(entry => {
if (!entry.isIntersecting) return; // Если элемент не видим, выходим
entry.target.classList.remove('section--hidden'); // Убираем класс
observer.unobserve(entry.target); // Прекращаем наблюдение
});
};

Настройки (options):
root: Область, относительно которой происходит наблюдение. Если null, это весь экран.
threshold: Процент видимости элемента, при котором срабатывает callback.

Добавление Observer к элементам:
allSections.forEach(section => sectionObserver.observe(section));

Как это работает пошагово?
Изначальное состояние:
Все секции скрыты (имеют класс section--hidden).

Когда секция попадает в видимость:
Observer вызывает callback-функцию.
Callback убирает класс section--hidden, делая секцию видимой.

Остановка наблюдения:
После того как секция стала видимой, мы больше за ней не наблюдаем:
observer.unobserve(entry.target);

Улучшения и дополнительные примеры:
Добавление разных анимаций для секций
Можно настроить разные анимации для секций, добавляя уникальные классы.

css
.section--hidden.section-1 {
transform: translateX(-50px); /_ Смещение влево _/
}
.section--hidden.section-2 {
transform: translateY(-50px); /_ Смещение вверх _/
}
.section--hidden.section-3 {
transform: translateX(50px); /_ Смещение вправо _/
}

Добавление эффекта к другим элементам:
Вы можете наблюдать за любыми элементами, например, за изображениями или кнопками.
Просто замените .section на нужный селектор:

const images = document.querySelectorAll('.lazy-image');
images.forEach(image => sectionObserver.observe(image));

Результат:
Теперь каждая секция плавно появляется при прокрутке.
Код оптимизирован: после появления элемента наблюдение за ним прекращается,
что улучшает производительность.

Это простой, но мощный пример использования Intersection Observer API,
который можно адаптировать для сложных задач, таких как ленивое (lazy)
загружаемое изображение или отслеживание видимости рекламы.

// ------------------------------------------------------------------------------- //

## ОТЛОЖЕННАЯ ЗАГРУЗКА ИЗОБРАЖЕНИЙ

Тема: Оптимизация загрузки изображений с помощью ленивой загрузки (lazy loading)
Почему это важно?
Изображения занимают много места и времени при загрузке веб-страниц.
Особенно это касается больших изображений с высоким разрешением.
Ленивую загрузку используют, чтобы загружать изображения только тогда,
когда пользователь почти прокрутил к ним, экономя время и ресурсы.
Это особенно полезно для пользователей с медленным интернетом или устройствами с низкой производительностью.

Что мы будем делать?
Мы создадим функциональность, которая:

Показывает маленькое изображение-заглушку (с низким разрешением) до тех пор,
пока большое изображение не будет загружено.
Использует фильтр размытия, чтобы маленькое изображение выглядело более привлекательно.
Подменяет маленькое изображение на большое, когда пользователь прокрутил страницу достаточно близко.

1. Устройство HTML
   Пример HTML-кода:

<div class="feature">
  <img
    class="lazy-img"
    src="low-res-image.jpg" <!-- изображение-заглушка -->
    data-src="high-res-image.jpg" <!-- настоящее большое изображение -->
    alt="Feature Image"
  />
</div>

src — путь к изображению-заглушке (низкое разрешение).
data-src — путь к изображению высокого разрешения (будет подгружено позже).
Класс lazy-img добавляет стиль размытия для изображения-заглушки.

2. Стили CSS
   Мы добавляем размытие, чтобы низкое качество изображения не бросалось в глаза.

Пример CSS:

.lazy-img {
filter: blur(20px);
transition: filter 0.3s;
}

.lazy-img.loaded {
filter: blur(0);
}
filter: blur(20px); делает изображение размытым.
transition: filter 0.3s; плавно убирает размытие, когда загружается настоящее изображение.
Класс loaded убирает эффект размытия.

3. Основной скрипт
   Создадим логику в JavaScript, чтобы загружать изображения только тогда,
   когда пользователь прокрутил страницу близко к ним.

Шаг 1. Выбираем все нужные изображения

const imgTargets = document.querySelectorAll('img[data-src]');
Этот код выбирает только изображения с атрибутом data-src.
Это гарантирует, что мы работаем только с изображениями, которые нуждаются в ленивой загрузке.

Шаг 2. Настройка IntersectionObserver

const loadImg = function (entries, observer) {
const [entry] = entries;

// Проверяем, если изображение не пересекает область видимости, ничего не делаем.
if (!entry.isIntersecting) return;

// Меняем путь изображения на настоящий.
entry.target.src = entry.target.dataset.src;

// После загрузки убираем размытие.
entry.target.addEventListener('load', function () {
entry.target.classList.remove('lazy-img');
});

// Прекращаем наблюдать за этим изображением.
observer.unobserve(entry.target);
};

// Создаем наблюдателя.
const imgObserver = new IntersectionObserver(loadImg, {
root: null,
threshold: 0,
rootMargin: '200px', // Начинаем загрузку за 200 пикселей до появления изображения.
});

// Наблюдаем за каждым изображением.
imgTargets.forEach(img => imgObserver.observe(img));

Как это работает:
IntersectionObserver наблюдает за изображениями.

Когда пользователь прокручивает страницу и изображение попадает в область видимости
(или близко к ней), срабатывает функция loadImg.

entry.isIntersecting проверяет, пересекает ли изображение область видимости.

Если пересекает, подменяем src на настоящее изображение (data-src).

Событие load:
Когда настоящее изображение загрузилось, мы убираем размытие, удаляя класс lazy-img.
observer.unobserve прекращает наблюдение за изображением, так как больше нет необходимости проверять его.

Дополнительные улучшения:
Отрицательный rootMargin:
Установка rootMargin: '200px' позволяет начать загрузку изображений
за 200 пикселей до их появления.
Это обеспечивает плавность, так как пользователь никогда не увидит пустое место.

Медленная загрузка для тестирования:
В браузерных инструментах разработчика можно настроить имитацию медленного интернета
(например, "Slow 3G"), чтобы протестировать, как ведет себя ленивое изображение.

Пример кода целиком:
// 1. Выбираем изображения
const imgTargets = document.querySelectorAll('img[data-src]');

// 2. Функция для загрузки изображения
const loadImg = function (entries, observer) {
const [entry] = entries;
if (!entry.isIntersecting) return;

// Подмена пути
entry.target.src = entry.target.dataset.src;

// Убираем размытие после загрузки
entry.target.addEventListener('load', function () {
entry.target.classList.remove('lazy-img');
});

// Прекращаем наблюдение
observer.unobserve(entry.target);
};

// 3. Создаем наблюдателя
const imgObserver = new IntersectionObserver(loadImg, {
root: null,
threshold: 0,
rootMargin: '200px',
});

// 4. Наблюдаем за изображениями
imgTargets.forEach(img => imgObserver.observe(img));

Что в итоге?
Теперь:
Маленькое изображение-заглушка отображается сразу.
Настоящее изображение загружается только тогда, когда пользователь приближается к нему.
Пользователь видит готовую страницу быстрее,
так как большие изображения загружаются только при необходимости.
Это улучшает производительность, делает страницу более отзывчивой и удобной для пользователей.

Я спросил у GPT:
Почему мы выбрали изображения с помощью этого кода:
const imgTargets = document.querySelectorAll('img[data-src]');
Если мы нигде не используем imgTargets.

ChatGPT сказал:
На самом деле, в коде мы используем переменную imgTargets.
Она нужна для того, чтобы получить список всех изображений с атрибутом data-src,
которые мы хотим наблюдать и для которых будет реализована ленивое загрузка.

Давайте разберем шаг за шагом:

1. Код выбора изображений
   const imgTargets = document.querySelectorAll('img[data-src]');

Этот код:
Использует метод querySelectorAll для поиска всех элементов img, у которых есть атрибут data-src.
Возвращает NodeList (список DOM-элементов), содержащий все найденные изображения.
Этот список сохраняется в переменной imgTargets.

Пример: Если у нас есть HTML:
<img src="placeholder1.jpg" data-src="real-image1.jpg" class="lazy-img" />
<img src="placeholder2.jpg" data-src="real-image2.jpg" class="lazy-img" />
<img src="placeholder3.jpg" data-src="real-image3.jpg" class="lazy-img" />
То imgTargets будет содержать список из трех элементов img.

2. Как используется imgTargets
   Позже мы используем эту переменную для цикла:

imgTargets.forEach(img => imgObserver.observe(img));

Здесь:
Метод forEach проходит по каждому изображению в списке imgTargets.
Для каждого изображения вызывается метод observe у imgObserver.
Это говорит нашему IntersectionObserver "наблюдать" за этим конкретным изображением.

Почему важно выбрать только нужные изображения?
Если бы мы выбрали все изображения на странице
(например, с помощью document.querySelectorAll('img')),
то:
Мы бы пытались наблюдать за изображениями, которые не требуют ленивой загрузки, например логотип или аватарки.
Это могло бы вызвать ошибки или ненужное использование ресурсов.
Именно поэтому мы выбираем только те изображения, у которых есть атрибут data-src,
так как именно они участвуют в ленивой загрузке.

Итог:
Переменная imgTargets необходима для:
Выбора изображений, которые требуют ленивой загрузки.
Обхода этих изображений в цикле forEach и подключения к ним IntersectionObserver.
Без нее наш код просто не знал бы, какие именно изображения нужно обрабатывать.

Я спросил у GPT:
Расскажи логику этого кода const [entry] = entries;
и еще хочу узнать что значит entry.target

ChatGPT сказал:
Логика кода const [entry] = entries;

1. Что такое entries?
   entries — это параметр, который передается в callback-функцию IntersectionObserver:

javascript:
const observer = new IntersectionObserver(callback, options);
Когда наблюдатель (observer) срабатывает, он передает массив entries.

Каждый элемент в entries — это объект типа IntersectionObserverEntry,
который содержит информацию об одном элементе, за которым наблюдает IntersectionObserver.

Например, если мы наблюдаем за несколькими изображениями,
каждое событие может содержать несколько записей (entries),
по одной на каждое наблюдаемое изображение.

2. Что делает const [entry] = entries;?
   Эта строка деструктурирует массив entries,
   извлекая первый элемент из массива и записывая его в переменную entry.

Эквивалент без деструктуризации:
const entry = entries[0];

Мы предполагаем, что в большинстве случаев entries содержит только одну запись,
так как обычно IntersectionObserver срабатывает для одного элемента за раз.

3. Почему const [entry] = entries;?
   Мы извлекаем только первый элемент, потому что обрабатываем по одному объекту за раз.
   Это упрощает код, делая его компактнее.

Логика entry.target:

1. Что такое entry?
   entry — это объект IntersectionObserverEntry.
   Он содержит информацию о наблюдаемом элементе.

2. Что значит entry.target?
   entry.target — это свойство объекта IntersectionObserverEntry,
   которое ссылается на HTML-элемент, за которым наблюдает IntersectionObserver.

Пример:
Если мы наблюдаем за изображением:
<img src="placeholder.jpg" data-src="real-image.jpg" class="lazy-img" />
То в момент, когда это изображение пересечет границу видимости (например, попадет в viewport),
entry.target будет ссылаться на этот конкретный элемент img.

3. Пример использования entry.target

const observerCallback = (entries, observer) => {
const [entry] = entries;

if (!entry.isIntersecting) return;

// Доступ к элементу, который пересек границу
const img = entry.target;

// Заменяем src на data-src
img.src = img.dataset.src;

// Убираем класс "lazy-img"
img.classList.remove('lazy-img');

// Перестаём наблюдать за этим элементом
observer.unobserve(img);
};

Объяснение кода:
Когда элемент пересекает границу, entry.target — это элемент, за которым наблюдаем.
С помощью img.src = img.dataset.src заменяем заглушку (placeholder) на настоящее изображение.
Снимаем эффект размытия, удаляя класс lazy-img.
Убираем наблюдение за этим элементом, так как он больше не требует ленивой загрузки.

Итог:
const [entry] = entries; извлекает первую запись из массива entries.
entry.target ссылается на HTML-элемент, за которым наблюдает IntersectionObserver,
чтобы мы могли работать с этим элементом напрямую (например, изменять его свойства).

Вы сказали:
То есть как я понял, изображения которая находится внутри <img src="placeholder.jpg">
загружается сразу при загрузке страницы браузера.
А изображения которая находится внутри data-src="real-image1.jpg"
не загружается при загрузке страницы браузера.

ChatGPT сказал:
Да, вы абсолютно правильно поняли!
Вот более подробное объяснение:

Что происходит:

1. Начальная загрузка страницы
   Атрибут src (<img src="placeholder.jpg">) указывает на "заглушку" (placeholder) изображения.
   Это маленькое, низкокачественное изображение, которое загружается сразу,
   как только страница загружается в браузере.

Оно имеет небольшой размер и быстро загружается, что ускоряет начальную загрузку страницы.
Атрибут data-src (data-src="real-image1.jpg") указывает на реальное,
большое изображение, которое пока не загружается.
Браузер не обрабатывает атрибут data-src автоматически.

2. Ленивая загрузка (Lazy Loading)
   Реальные изображения из data-src загружаются только тогда,
   когда пользователь начинает прокручивать страницу, и эти изображения появляются
   (или приближаются) к области видимости (viewport).

Это достигается с помощью JavaScript и API IntersectionObserver.
Код отслеживает момент, когда изображение становится видимым,
и:
Копирует содержимое data-src в src (img.src = img.dataset.src).
Браузер автоматически загружает изображение, потому что теперь оно указано в src.

Почему это полезно?
Оптимизация производительности:
Если у вас на странице много изображений, загружать их все сразу — дорогостоящая операция.
Это увеличивает время загрузки страницы и может привести к задержкам.

Экономия ресурсов:
Пользователь загружает только те изображения, которые ему действительно нужны (которые он видит).

Улучшение пользовательского опыта:
Вместо долгой загрузки всех изображений, пользователь быстрее видит содержимое страницы (заглушки),
пока реальные изображения догружаются по мере необходимости.

Визуальная схема:
При загрузке страницы:
<img src="placeholder.jpg" data-src="real-image1.jpg" class="lazy-img">
<img src="placeholder.jpg" data-src="real-image2.jpg" class="lazy-img">
placeholder.jpg загружается сразу.
real-image1.jpg и real-image2.jpg не загружаются.

Когда пользователь прокручивает страницу:
JavaScript замечает, что изображение попало в область видимости.

Код выполняет:
img.src = img.dataset.src; // Заменяет "placeholder.jpg" на "real-image1.jpg"
img.classList.remove('lazy-img'); // Убирает эффект размытия
Браузер загружает настоящее изображение.

Итог:
src: Загружается сразу (заглушка).
data-src: Ожидает, пока JavaScript инициирует его загрузку (ленивая загрузка).

// ------------------------------------------------------------------------------- //

## СОЗДАНИЕ КОМПОНЕНТА СЛАЙДЕРА - ЧАСТЬ 1

Хорошенько подумай сперва было трудно понять, но когда разбирал это вслух все стало отлично.

Давайте подробно разберем логику работы слайдера, шаг за шагом, объясняя каждую строку кода.
Слайдер — это компонент, который позволяет пользователю переключаться между слайдами.
Сначала мы разберем основные элементы и принципы, а затем рассмотрим сам код.

Основные принципы слайдера:
HTML структура:

У нас есть контейнер для слайдов (slider), в котором размещены слайды (slide).
Каждый слайд располагается рядом друг с другом в одной строке (с помощью CSS).

CSS стили:
Используется свойство overflow: hidden, чтобы показать только одну часть слайдов.
Слайды перемещаются с помощью transform: translateX(...), изменяя их горизонтальное положение.

JavaScript логика:
Мы меняем положение слайдов, когда пользователь нажимает кнопки переключения.
Движение происходит за счет изменения значения translateX.

Теперь разберем код.

1. Установка начального положения слайдов

Код:
const slides = document.querySelectorAll('.slide');
slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * i}%)`;
});

Объяснение:
document.querySelectorAll('.slide'):
Находит все элементы с классом slide и возвращает их в виде списка.
Этот список сохраняется в переменной slides.

slides.forEach((s, i) => {...}):
Перебираем каждый слайд (s) с его индексом (i).
Для каждого слайда задается его горизонтальное положение с помощью transform: translateX.

transform: translateX(...):
Перемещает элемент по оси X на определенное расстояние.
Формула 100 \* i означает, что:
Первый слайд (индекс 0) остаётся на месте (0%).
Второй слайд (индекс 1) перемещается на 100% вправо.
Третий слайд (индекс 2) на 200%, и так далее.

2. Переключение на следующий слайд

Код:
let currentSlide = 0;
const maxSlide = slides.length - 1;

const nextSlide = () => {
if (currentSlide === maxSlide) {
currentSlide = 0; // Возвращаемся к первому слайду
} else {
currentSlide++;
}

slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * (i - currentSlide)}%)`;
});
};

Объяснение:
let currentSlide = 0;:
Переменная, которая отслеживает текущий слайд. Начинаем с первого слайда (индекс 0).

const maxSlide = slides.length - 1;:
Определяем индекс последнего слайда. Если у нас 4 слайда, их индексы будут 0, 1, 2, 3.
Поэтому последний индекс — это длина массива минус 1.

if (currentSlide === maxSlide) {...}:
Проверяем, достигли ли мы последнего слайда. Если да, то возвращаемся к первому (currentSlide = 0).

else { currentSlide++; }:
Если мы ещё не на последнем слайде, увеличиваем индекс текущего слайда на 1 (currentSlide++).

slides.forEach((s, i) => {...}):
Перебираем все слайды.

s.style.transform = translateX(${100 _ (i - currentSlide)}%):
Для каждого слайда рассчитываем новое положение.
Формула 100 _ (i - currentSlide) делает следующее:
Для текущего слайда (например, currentSlide = 1) его положение станет 0%.
Слайд перед ним переместится на -100%.
Слайд после него переместится на 100%.

3. Переключение на предыдущий слайд

Код:
const prevSlide = () => {
if (currentSlide === 0) {
currentSlide = maxSlide; // Возвращаемся к последнему слайду
} else {
currentSlide--;
}

slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * (i - currentSlide)}%)`;
});
};

Объяснение:
if (currentSlide === 0):
Если текущий слайд первый, переходим к последнему (currentSlide = maxSlide).

else { currentSlide--; }:
В ином случае уменьшаем индекс текущего слайда на 1 (currentSlide--).
Логика перемещения слайдов такая же, как в функции nextSlide.

4. Инициализация слайдера

Код:
const goToSlide = (slide) => {
slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * (i - slide)}%)`;
});
};

goToSlide(0); // Устанавливаем первый слайд активным

Объяснение:
goToSlide(slide):

Функция принимает номер слайда (slide) и перемещает все слайды таким образом,
чтобы указанный слайд стал текущим.

goToSlide(0):
Устанавливает начальное состояние слайдера, где первый слайд активен.

Как работает вся логика?
Начальное состояние:
Слайды выстраиваются в ряд, и видим только первый слайд.
Это достигается с помощью начальной настройки translateX и overflow: hidden.

Кнопки переключения:
Каждое нажатие на кнопку изменяет переменную currentSlide.
Затем пересчитываются позиции всех слайдов.

Бесконечный цикл:
Если мы достигли последнего слайда, то возвращаемся к первому (и наоборот).

Пример целого кода:
const slides = document.querySelectorAll('.slide');
let currentSlide = 0;
const maxSlide = slides.length - 1;

// Устанавливаем начальное положение
const goToSlide = (slide) => {
slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * (i - slide)}%)`;
});
};
goToSlide(0);

// Переключение на следующий слайд
const nextSlide = () => {
if (currentSlide === maxSlide) {
currentSlide = 0;
} else {
currentSlide++;
}
goToSlide(currentSlide);
};

// Переключение на предыдущий слайд
const prevSlide = () => {
if (currentSlide === 0) {
currentSlide = maxSlide;
} else {
currentSlide--;
}
goToSlide(currentSlide);
};

// Пример использования (например, кнопки)
document.querySelector('.btn-next').addEventListener('click', nextSlide);
document.querySelector('.btn-prev').addEventListener('click', prevSlide);

Давайте подробно разберем код функции goToSlide и логики её работы.
Код функции:
const goToSlide = (slide) => {
slides.forEach((s, i) => {
s.style.transform = `translateX(${100 * (i - slide)}%)`;
});
};
goToSlide(0);

Что делает goToSlide:
Функция goToSlide отвечает за отображение нужного слайда.
Она перемещает каждый слайд в нужное положение с помощью CSS-свойства transform: translateX().

Логика работы:
Входной параметр:
slide: номер слайда, который мы хотим сделать текущим (например, 0 для первого, 1 для второго, и т.д.).

Пошаговый разбор:

1. Цикл по слайдам:

slides.forEach((s, i) => { ... });
slides — это коллекция (NodeList) всех элементов с классом slide.
forEach перебирает каждый элемент из этой коллекции.
s — текущий слайд.
i — индекс текущего слайда (0, 1, 2 и т.д.).
Цель цикла — для каждого слайда определить, куда он должен быть перемещен в
зависимости от его индекса i и текущего слайда slide.

2. Вычисление значения translateX:

s.style.transform = `translateX(${100 * (i - slide)}%)`;
Эта строка устанавливает CSS-свойство transform для каждого слайда.

Разберем выражение внутри translateX:
Формула:
100 \* (i - slide)
i — индекс текущего слайда.
slide — индекс текущего активного слайда.

Объяснение:
С помощью разницы i - slide мы определяем относительное положение текущего слайда i
относительно активного слайда slide.
Умножение на 100 преобразует разницу в проценты, что соответствует ширине одного слайда.

Примеры:
Когда slide = 0 (первый слайд активен):

Для слайда с индексом i = 0:
translateX = 100 \* (0 - 0) = 0%
Слайд остаётся на месте.

Для слайда с индексом i = 1:
translateX = 100 \* (1 - 0) = 100%
Слайд перемещается вправо на 100% своей ширины.

Для слайда с индексом i = 2:
translateX = 100 \* (2 - 0) = 200%
Слайд перемещается вправо на 200%.

Когда slide = 1 (второй слайд активен):

Для слайда с индексом i = 0:
translateX = 100 \* (0 - 1) = -100%
Слайд перемещается влево на 100%.

Для слайда с индексом i = 1:
translateX = 100 \* (1 - 1) = 0%
Второй слайд становится активным (остаётся на месте).

Для слайда с индексом i = 2:
translateX = 100 \* (2 - 1) = 100%
Слайд перемещается вправо на 100%.

3. Установка стиля:

javascript:
s.style.transform = `translateX(...)`;
Эта строка применяет вычисленный translateX к каждому слайду, перемещая его на нужное место.

Начальное состояние:
goToSlide(0);
Вызов goToSlide(0) устанавливает первый слайд активным:
Первый слайд (i = 0) остаётся на месте (translateX(0%)).
Второй слайд (i = 1) перемещается вправо (translateX(100%)).
Третий слайд (i = 2) перемещается ещё дальше вправо (translateX(200%)).

Как работает переключение слайдов:
Когда мы переключаемся на другой слайд, например, вызывая goToSlide(1):
Каждый слайд получает новое значение translateX.

Это визуально перемещает слайды так, чтобы выбранный слайд оказался в центре (на позиции 0%),
а остальные — слева или справа от него.

Итог:
Функция goToSlide управляет положением всех слайдов,
вычисляя их относительное смещение на основе активного слайда.
Это делается динамически с помощью формулы 100 \* (i - slide) и CSS-свойства transform.

// ------------------------------------------------------------------------------- //

## СОЗДАНИЕ КОМПОНЕНТА СЛАЙДЕРА - ЧАСТЬ 2

1. Обработка событий клавиатуры
   Идея:
   Мы добавляем возможность перемещаться по слайдам
   с помощью клавиш стрелок (ArrowLeft и ArrowRight).

Логика:
Слушатель событий: Мы добавляем слушатель событий keydown на объект document.
Это позволяет обрабатывать нажатия клавиш в любом месте страницы.

javascript:
document.addEventListener('keydown', function (e) {
if (e.key === 'ArrowLeft') {
previousSlide(); // Переключение на предыдущий слайд
}
if (e.key === 'ArrowRight') {
nextSlide(); // Переключение на следующий слайд
}
});
e — объект события, который содержит информацию о событии,
включая свойство key, определяющее, какая клавиша была нажата.

Функции переключения слайдов: Эти функции уже реализованы в коде:

function nextSlide() {
// Логика перехода к следующему слайду
}

function previousSlide() {
// Логика перехода к предыдущему слайду
}

2. Создание точек навигации
   Идея:
   Под слайдером создаются маленькие "точки" (кнопки), каждая из которых соответствует определенному слайду.
   Клик по точке переключает на соответствующий слайд.

Логика:
HTML-структура:
У нас уже есть пустой контейнер для точек:

<div class="dots"></div>
Сюда мы будем добавлять элементы точек.

Создание точек программно:
Создадим функцию, которая добавляет точки в контейнер.
Она создает по одной кнопке для каждого слайда.

function createDots() {
slides.forEach((\_, i) => {
dotContainer.insertAdjacentHTML(
'beforeend',
`<button class="dots__dot" data-slide="${i}"></button>`
);
});
};
slides — это массив слайдов.
data-slide="${i}" — добавляем атрибут, который связывает точку с номером слайда.

Вызов функции: Мы вызываем createDots() при инициализации слайдера:
createDots();

3. Обработка кликов по точкам
   Идея:
   Когда пользователь кликает по точке, слайдер переключается на соответствующий слайд.

Логика:
Слушатель событий:
Мы используем делегирование событий.
Вместо того чтобы назначать обработчик на каждую точку,
мы добавляем один обработчик на общий контейнер точек.

javascript:
dotContainer.addEventListener('click', function (e) {
if (e.target.classList.contains('dots\_\_dot')) {
const { slide } = e.target.dataset; // Получаем номер слайда
goToSlide(slide); // Переходим к соответствующему слайду
}
});
e.target — элемент, на который пользователь кликнул.
dataset.slide — значение атрибута data-slide.

4. Активация текущей точки
   Идея:
   Сделаем так, чтобы активная точка подсвечивалась, показывая текущий слайд.

Логика:
Деактивация всех точек:
Убираем класс dots\_\_dot--active у всех точек.

document
.querySelectorAll('.dots**dot')
.forEach(dot => dot.classList.remove('dots**dot--active'));

Активация нужной точки: Добавляем класс dots\_\_dot--active только нужной точке:

document
.querySelector(`.dots__dot[data-slide="${Slide}"]`)
.classList.add('dots\_\_dot--active');

5.  Инициализация и улучшения кода
    Идея:
    Объединим все действия по настройке слайдера в одну функцию
    и защитим глобальное пространство имен.

    Логика:
    Функция init:
    Создаем функцию инициализации, где вызываем все необходимые действия:

    function init() {
    createDots();
    activateDot(0); // Активируем точку для первого слайда
    goToSlide(0); // Переходим к первому слайду
    }
    init();

    Обертка всего кода:
    Чтобы избежать конфликтов с другими частями программы,
    помещаем весь код слайдера в анонимную функцию:

    (function () {
    // Весь код слайдера
    })();

    Пример: Как это выглядит вместе
    Вот полная версия слайдера с комментариями:

    (function () {
    const slides = document.querySelectorAll('.slide');
    const dotContainer = document.querySelector('.dots');
    let currentSlide = 0;

        function goToSlide(slide) {
            slides.forEach((s, i) => (s.style.transform = `translateX(${100 * (i - slide)}%)`));
        }

        function createDots() {
            slides.forEach((_, i) => {
                dotContainer.insertAdjacentHTML(
                    'beforeend',
                    `<button class="dots__dot" data-slide="${i}"></button>`
                );
            });
        }

        function activateDot(slide) {
            document
                .querySelectorAll('.dots__dot')
                .forEach(dot => dot.classList.remove('dots__dot--active'));

            document
                .querySelector(`.dots__dot[data-slide="${slide}"]`)
                .classList.add('dots__dot--active');
        }

        document.addEventListener('keydown', function (e) {
            if (e.key === 'ArrowLeft') previousSlide();
            if (e.key === 'ArrowRight') nextSlide();
        });

        dotContainer.addEventListener('click', function (e) {
            if (e.target.classList.contains('dots__dot')) {
                const { slide } = e.target.dataset;
                goToSlide(slide);
                activateDot(slide);
            }
        });

        function init() {
            createDots();
            activateDot(0);
            goToSlide(0);
        }

        init();

    })();

Итог:
Теперь у вас есть базовый функционал слайдера:
клавиши стрелок, точки навигации, инициализация и управление активными элементами.
Вы можете настроить стили и добавить дополнительные функции (например, автопрокрутку).

// ------------------------------------------------------------------------------- //

## СОБЫТИЯ DOM ЖИЗНЕННОГО ЦИКЛА

1. Событие DOMContentLoaded
   Что это?
   Событие DOMContentLoaded срабатывает, когда HTML-документ
   полностью загружен и разобран в DOM-дерево.
   При этом скрипты внутри HTML должны быть загружены и выполнены.
   Однако изображения и другие внешние ресурсы (например, стили CSS) могут загружаться позже.

Как использовать?
Вы можете использовать это событие, чтобы выполнить
определенный код сразу после того, как DOM готов к взаимодействию.

Пример:

document.addEventListener('DOMContentLoaded', function () {
console.log('HTML полностью загружен и разобран');
// Здесь можно писать код, который работает с DOM
document.body.style.backgroundColor = 'lightblue';
});

Разбор кода:
Мы добавляем обработчик события к document.
Внутри функции пишем действия, которые хотим выполнить, когда DOM готов.

Почему не всегда нужно это событие?
Если ваш скрипт подключен в конце body HTML-документа,
он автоматически выполнится после разбора HTML.

Например:

<body>
    <h1>Пример</h1>
    <script>
        console.log('HTML разобран, скрипт выполняется');
    </script>
</body>
Здесь событие DOMContentLoaded уже не нужно.

2. Событие load
   Что это?
   Событие load срабатывает, когда вся страница полностью загружена,
   включая изображения, стили CSS и другие ресурсы.

Как использовать?
Вы можете использовать это событие, чтобы запустить код,
который должен выполниться только после полной загрузки всех ресурсов.

Пример:
window.addEventListener('load', function () {
console.log('Страница полностью загружена');
const img = document.createElement('img');
img.src = 'https://example.com/image.jpg';
document.body.appendChild(img);
});

Разбор кода:
Обработчик добавляется к window.
После полной загрузки страницы в консоли появляется сообщение.
Мы динамически добавляем изображение.

Когда использовать?
Если ваш код зависит от изображений или других ресурсов (например, слайдер),
лучше использовать load. Например, для галереи изображений.

3. Событие beforeunload
   Что это?
   Событие beforeunload возникает, когда пользователь собирается покинуть страницу
   (например, закрыть вкладку, перезагрузить страницу или перейти на другой URL).

Как использовать?
Вы можете использовать это событие, чтобы предупредить пользователя,
если он может потерять несохраненные данные.

Пример:
window.addEventListener('beforeunload', function (event) {
event.preventDefault(); // Иногда требуется для активации события
event.returnValue = ''; // Показывает стандартное предупреждение
});

Разбор кода:
Добавляется обработчик к window.
Устанавливается event.returnValue, чтобы браузер показал стандартное сообщение.

Ограничения:
Браузеры больше не позволяют настраивать сообщение, чтобы избежать злоупотреблений.
Используйте это событие только в важных случаях (например, пользователь заполняет форму).
Пример ситуации:
Пользователь пишет длинное сообщение в блоге.
Если он случайно закроет вкладку, сообщение может быть потеряно.
В таком случае стоит предупредить его.

Дополнительные пояснения
Когда какой метод использовать?

DOMContentLoaded: Для выполнения кода, который работает только с DOM (без изображений).
load: Когда ваш код зависит от полного завершения загрузки страницы.
beforeunload: Для защиты данных пользователя от случайной потери.

Почему не стоит злоупотреблять beforeunload?
Это может раздражать пользователей, если они видят сообщение без реальной причины.

Отличие от jQuery:
Если вы ранее использовали jQuery, там есть метод $(document).ready().
Это эквивалентно DOMContentLoaded в чистом JavaScript.

Пример в jQuery:
$(document).ready(function () {
console.log('DOM готов');
});

Итог:
События DOM помогают управлять загрузкой и взаимодействием со страницей.

Вот основные моменты:
Используйте DOMContentLoaded для раннего запуска кода.
Используйте load для кода, который зависит от полной загрузки страницы.
Используйте beforeunload с осторожностью, только для предупреждений о возможной потере данных.

// ------------------------------------------------------------------------------- //

## ЭФФЕКТИВНАЯ ЗАДЕРЖКА ЗАГРУЗКИ СКРИПТА И АСИНХРОННОСТЬ

Способы подключения JavaScript в HTML:
В HTML мы можем подключать JavaScript разными способами,
которые влияют на порядок загрузки и выполнения кода.

1. Обычное подключение скрипта
   Это самый базовый способ:

<head>
    <script src="script.js"></script>
</head>

Что происходит?
Браузер начинает разбирать HTML (создает DOM-дерево).
Когда он встречает тег script он останавливает разбор HTML.
Загружает файл script.js с сервера.
Выполняет содержимое файла.
Возобновляет разбор HTML.

Проблема:
Это замедляет загрузку страницы, так как HTML не может быть
полностью обработан до загрузки и выполнения скрипта.

2. Скрипт в конце body
   Часто скрипты размещают в самом конце документа:

<body>
    <script src="script.js"></script>
</body>

Что происходит?
Браузер разбирает весь HTML и создает DOM-дерево.
Только после завершения разбора HTML начинается загрузка и выполнение скрипта.

Почему это лучше?
HTML загружается полностью до выполнения скриптов.
DOM уже готов, когда скрипт начинает выполняться.

3. Атрибут async
   С помощью атрибута async можно загружать скрипт асинхронно:

<head>
    <script src="script.js" async></script>
</head>

Что происходит?
Браузер начинает разбирать HTML.
Одновременно с этим загружается script.js.
Как только скрипт загрузится, его выполнение немедленно прерывает разбор HTML.

Преимущество:
Скрипт загружается параллельно с разбором HTML, что ускоряет загрузку.

Недостаток:
Разбор HTML временно прерывается, когда скрипт начинает выполняться.
Порядок выполнения скриптов не гарантирован.
Если есть несколько async-скриптов, они выполняются в том порядке, в котором загрузились.

4. Атрибут defer
   С помощью атрибута defer можно указать браузеру
   отложить выполнение скрипта до завершения разбора HTML:

<head>
    <script src="script.js" defer></script>
</head>

Что происходит?
Скрипт загружается параллельно с разбором HTML.
Выполняется только после того, как HTML полностью разобран.

Преимущество:
HTML парсится без остановок.
Скрипты выполняются в порядке их объявления в HTML.

Сравнение async и defer:
Характеристика
Загрузка:
async - Асинхронная (одновременно с HTML).
defer - Асинхронная (одновременно с HTML).

Выполнение:
async - Сразу после загрузки.
defer - После полного разбора HTML.

Влияние на HTML:
async - Останавливает разбор HTML.
defer - Не прерывает разбор HTML.

Гарантия порядка:
async - Нет.
defer - Да.

Использование:
async - Внешние скрипты, не зависящие от DOM.
defer - Скрипты, взаимодействующие с DOM.

Как выбрать способ подключения?

Обычный скрипт (без атрибутов в <head>):
Никогда не используйте этот способ, так как он сильно замедляет загрузку страницы.

Скрипт в конце body:
Используйте, если вы хотите избежать остановки разбора HTML
и не хотите думать о async или defer.

Скрипт с async:
Подходит для сторонних скриптов (например, Google Analytics, реклама).
Порядок выполнения не важен.

Скрипт с defer:
Используйте для своих скриптов, которые работают с DOM.
Гарантирует выполнение в правильном порядке.

Пример использования:

Предположим, у вас есть:
Сторонний аналитический скрипт.
Ваш собственный код, который зависит от библиотеки.

Решение:

<head>
    <script src="analytics.js" async></script> <!-- Аналитика -->
    <script src="library.js" defer></script>  <!-- Библиотека -->
    <script src="app.js" defer></script>      <!-- Ваш код -->
</head>

analytics.js загружается и выполняется как только готов.
library.js и app.js загружаются параллельно, но выполняются строго
в указанном порядке после полного разбора HTML.

Как проверить поведение?
Открыть "Сеть" (Network) в инструментах разработчика:
Посмотрите, как загружаются ресурсы и в каком порядке.

Вывод:
Для своих скриптов лучше всего использовать defer.
Он обеспечивает корректный порядок выполнения и не мешает разбору HTML.
Для сторонних скриптов, где порядок не важен, используйте async.
Старые браузеры игнорируют async и defer,
поэтому в таких случаях скрипты лучше размещать в конце body.
```
