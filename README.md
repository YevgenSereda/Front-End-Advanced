# Основы HTML

Front-end состоит из трех частей/технологий/языков:

  - HTML
  - CSS
  - JavaScript

Каждая отвечает за свой определенный диапазон задач.

# HTML (HyperText Markup Language)

Служит для описания логической структуры веб-страницы

```html
<div class="card-body">
	<span class="icon-user head-icon"></span>
	<h3>For <b>kandidater</b></h3>
	<p>Bloom hjælper kandidater med en proffessionel og målrettet 	proces frem mod the bedste match.</p>
	<a href="#" class="link">
		<span class="icon-chevron-right"></span>
	</a>
</div>
```

# CSS (Cascading Style Sheets)

Служит для оформления внешнего вида документа

```css
.map-popup {
	background: #fff;
	border-bottom: 4px solid #e36018;
	position: absolute;
	top: 10px;
	left: 20px;
	z-index: 4;
	font-size: 12px;
	font-weight: 400;
	max-width: 200px;
	width: 100%;
}
```

# JavaScript

Служит для добавления интерактивности веб-страницам

```js
CustomMap.prototype = {
	getNearestMarkers: function(){
		self = this;
		return this.allMarkers.filter(function(marker){
			return self.getDistance(marker) <= self.options.mapOptions.distance;
		});
	},
	setNearestMarkers: function(){
		var activeFilters = this.filters.filter(':checked');
		if(activeFilters.length){
			activeFilters[0].checked = false;
			jcf.refresh(activeFilters[0]);
		}
		this.removeAllMarkers();
		this.appendMarkers(this.nearestMarkers);

	}
};
```
# Общий вид структуры HTML

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Заголовок страницы</title>
		<link media="all" rel="stylesheet" href="css/main.css">
	</head>
	<body>
		контент
	</body>
</html>
```
HTML код состоит из элементов - тэгов. Структура тэга:
```html
<тэг атрибут="значение">контент</тэг>
```
В качестве контента могут выступать как текст/графика, так и другие тэги (элементы).
В HTML есть три корневых элемента. Основной корневой элемент - html - указывает браузеру начало и конец страницы. Непосредственно внутри html может находиться только два элемента: head и body. В head находятся служебные элементы, необходимые для правильного отображения страницы (заголовок страницы, подключения стилей, скриптов и шрифтов, ключевые слова для поисковиков и т.д.). В body находится весь контент страницы.
Существует множество различных элементов, отвечающих за вывод различного контента (текст, картинки, формы ввода и т.д.).
Для примера добавим обычную ссылку. В HTML для ссылок используется элемент а:
```html
<a>Hello world!</a>
```
В браузере стандартная ссылка - синего цвета и с подчеркиванием. Обычно ссылка ведет на другую страницу, но сейчас при клике на нее ничего не происходит - потому что не указан адрес, по которому нужно перейти при клике. Для задания адреса у ссылки есть обязательный атрибут href:
```html
<a href="">Hello world!</a>
```
В кавычках (т.е. в значении атрибута) необходимо указать нужный адрес. Адреса бывают относительные и абсолютные. 
# Абсолютные и относительные адреса
Относительный адрес - это адрес, который указывается относительно расположения текущего файла. Например, в папке проекта есть папка images, в которой лежит файл image.jpg. Чтобы добавить адрес этой картинки в ссылку нужно указать путь от файла index.html к файлу image.jpg:
```html
<a href="images/image.jpg">Hello world!</a>
```
Абсолютный адрес - это полный адрес страницы (или файла) в интернете, включая http:// . Например,
```html
<a href="https://www.google.com/">Hello world!</a>
```
# Строчные и блочные элементы
Разделим ссылку на две:
```html
<a href="https://www.google.com/">Hello</a>
<a href="https://www.google.com/">world!</a>
```
В браузере ссылки выстроились одна за другой слева направо - как слова в книге. Такие элементы называются строчными (inline) - это элементы, которые занимают только то пространство, которое ограничено тегами, определяющими строчный элемент (необходимое для отображения их содержимого) и не нарушая потока содержимого (не требующее новой строки после каждого элемента). То есть они занимают ровно столько места, сколько нужно для их контента. Управлять через CSS шириной, высотой и отступами для строчных элементов нельзя.
Кроме ссылок существует множество других строчных элементов: i (для выделения курсивом), strong (для выделения жирным), img (для вставки изображения), span (универсальный элемент для стилизации через CSS).
В книгах кроме отдельных слов есть также целые блоки с текстом, которые позволяют более красиво и логично структурировать текст - абзацы. Есть абзацы и в HTML - элемент p (paragraph). Добавим после ссылок два абзаца с произвольным текстом:
```html
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum, sunt!</p>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum, sunt!</p>
```
В браузере абзацы идут один за другим по вертикали, не сливаясь, между ними присутствуют отступы. Такие элементы называются блочными (block) - элементы, которые занимают всю ширину своего родителя (контейнера), формально создавая "блок". Браузеры обычно отображают блочные элементы с переводом строки до и после элемента. То есть даже если внутри абзаца очень мало контента (или вообще нет), то любой элемент после него начнется с новой строки. У блочных элементов можно управлять габаритами и отступами по горизонтали и вертикали независимо от их контента.
Существует также множество различных блочных элементов: заголовки (h1-h6), списки (ol - нумерованный, ul - ненумерованный), div (универсальный блок для стилизации). Например:
```html
<div>
	<h1>Front End</h1>
	<ol>
		<li>HTML</li>
		<li>CSS</li>
		<li>JavaScript</li>
	</ol>	
</div>
<div>
	<h2>A-level</h2>
	<ul>
		<li>FULLSTACK JS</li>
		<li>PHP</li>
		<li>FRONT-END</li>
		<li>.NET/C#</li>
		<li>JAVA</li>
		<li>ОСНОВЫ ПРОГРАММИРОВАНИЯ</li>
		<li>WEB-DESIGN</li>
		<li>HR/RECRUITMENT</li>
		<li>PROJECT MANAGEMENT</li>
		<li>JAVA-ANDROID</li>
		<li>QA AUTOMATION</li>
	</ul>
```
Важно обратить внимание, что непосредственно внутри списков ol и ul могут лежать только элементы li (list item).
# Структура CSS
Таким образом, с помощью HTML можно создать "скелет" страницы, внести логику и структурированность в поток контента. Чтобы каким-либо образом изменить стандартное отображение элементов в браузере используется CSS. Общий вид структуры CSS:
```css
селектор {
	свойство: значение;
}
```
Селектор - это обращение к элементу или элементам, к которым будут применяться определенные стили, это "адрес" элемента в общем потоке контента. Например, чтобы задать цвет фона для заголовка h1 достаточно написать так:
```css
h1 {
	background-color: yellow;
}
```
При таком селекторе (селектор по тэгу) все заголовки h1 на всей странице получат желтый фон. Часто это неудобно - одинаковые элементы могут иметь значительные различия в дизайне. Иногда эту проблему можно решить усложняя селектор:
```css
div h1 {
	background-color: yellow;
}
```
Желтый фон применится только к тем заголовкам, которые лежат внутри элемента div.
# Классы и id
Другим решением является указание более точного адреса нужного элемента с помощью специальных атрибутов - id и классов.
Id - это уникальный идентификатор элемента и позволяет привязать стили к одному конкретному элементу на странице. В CSS обращение к id осуществляется с помощью символа #. Например:
```html
<ol>
	<li id="item">HTML</li>
	<li>CSS</li>
	<li>JavaScript</li>
</ol>	
```
```css
#item {
	color: red;
}
```
Класс - это универсальный идентификатор для всех элементов на странице, имеющих одинаковый дизайн. В CSS обращение к классу осуществляется через точку:
```html
<ol>
	<li class="list-item">HTML</li>
	<li class="list-item">CSS</li>
	<li>JavaScript</li>
</ol>	
```
```css
.list-item {
	color: green;
}
```
Требования к именам классов и id одинаковы: допускается использование только букв латинского алфавита, цифр, дефиса и подчеркивания, начинаться имя должно с буквы.
Селекторы по классу и id могут комбинироваться с любыми другими:
```html
<h1 class="text">Front End</h1>
<ol>
	<li class="text">HTML</li>
	<li class="text">CSS</li>
	<li id="text-id">JavaScript</li>
</ol>	
```
```css
ol .text {
	color: green;
}

.text#text-id {
	color: red;
}
```
Первый селектор обращается ко всем элементам с классом .text, которые лежат внутри элемента ol. Заголовок лежит за пределами списка, поэтому зеленый цвет текста к нему не применился. Второй селектор обращается к элементу с id #text-id, если при этом он имеет класс .text. Последний элемент в списке имеет указанный id, но не имеет класса, поэтому цвет текста не изменился.
