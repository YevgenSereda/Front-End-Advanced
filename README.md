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

# CSS (Cascading Style Sheets)

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
Существует множество различных элементов, отвечающих за вывод различного контента (текст, картинки, формы ввода и т.д.). Например, элемент <p> используется для вывода абзаца текста, элемент <a> - для ссылки.

