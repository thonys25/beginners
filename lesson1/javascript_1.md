# 2. Основы JavaScript
[![test](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

### 3.1 ECMAScript
ECMAScript - это стандарт языка JavaScript. Приложение, которое мы сегодня написали, на 95% написано с использованием последнего стандарта ECMAScript 6 (далее ES6) и выше.

#### В чем, собственно, разница между ES5 и ES6 и другими?
Дело в том, что некоторые устройства могут не поддерживать тот или иной стандарт ECMAScript (далее ES). Это приводит к тому, что на сайтах магическим образом перестают работать кнопки, меню, ссылки, не получается что-то загрузить или просто просмотреть сайт. Так как пользователи сайтов - это обычные люди, которые не покупают себе мобильное устройство по-настроению или каждые полгода-год, то этому нужно уделять (а некоторые ещё и не обновляют версию iOS и(или) Android на своих устройствах), то это приводит к тому, что пользователь заходит на сайт, не может, например, зарегистрироваться (создать аккаунт на сайте) и уходит к конкуренту. Таким обраом вы (или компания, где вы работаете, теряет деньги и клиентов). Соответственно, чем больше компания, тем больше потери.

Чтобы избежать этой неприятной ситуации желательно иметь при себе устройство хотя бы 3-х летней давности, чтобы можно было протестировать работоспособность сайта, как на новых, так и на старых устройствах.

#### Лирическое отступление
В нынешних реалиях старшие и ведущие разработчики, как правило не заморачиваются на работоспособности сайтов (и даже мобильных приложений из App Store и Play Market) на устройствах даже 2-х - 3-х летней давности, по-видимому, считая таких людей неплатежеспособной аудиторией или просто желая показать, что они используют все самые последние новшества и идут таким образом в ногу со временем, а то что у части клиентов не работает сайт или приложение - это их проблемы. Пусть покупают себе новый девайс.


### 3.2 Базовый синтаксис
Мы будем разрабатывать приложение с использованием ES6 и выше, т.к. без него сейчас трудно куда-либо устроиться. Однако для понимания я буду приводить примеры и для более старых устройств, если таковые будут. 

P.S. Поскольку ES6+ привнес новые функции и методы, которых не было в ES5, например, то не всегда будет возможность привести альтернативный пример на ES с поддержкой устройств 3-5 летней давности.

#### Переменные и константы
В ES6 впервые стало возможным объявлять переменные с помощью let и const (помимо var)

#### Пример
index.html
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

    <div id="app"></div>

    <script type="text/javascript" src="app.js"></script>

</body>
</html>
```
app.js
```
let a = 10; //  Mutable переменная (т.е. переменная, значение которой может быть изменено далее в коде)
const b = 5;    //  Immutable переменная (т.е. переменная, значение которой не может быть изменено далее в коде,
т.к. Immutable - это всегда константное значение)

// a = 20; //  Значение переменной a изменится с 10 на 20, всё будет работать
// b = 15; // Ошибка, нельзя менять значение Immutable переменной (константы)

console.log(a + b); //  Результат 15
```
До этого, в ES5 использовалась запись следующего типа:

#### Пример
index.html
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

    <div id="app"></div>

    <script type="text/javascript" src="app.js"></script>

</body>
</html>
```
app.js
```
var a = 10; //  Эту переменную можно менять далее в коде сколько угодно раз, в том числе и менять её тип данных

// a = "Hello"; // Изменили тип данных с Number на String и приложение всё-равно работает. Вот такая вот магия.
```

### Этот вопрос задают на собеседовании.
[Разница между let и var](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Statements/let)

### Селекторы
До ES6 в JavaScript основными были следующие селекторы:

1. document.getElementById
2. document.getElementsByClassName
3. document.getElementByTagName

У каждого из этих селекторов свое назначение. Вот примеры, как применяется каждый из этих селекторов.

#### Пример - document.getElementById (ES5)
index.html
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

    <div id="app"></div>

    <script type="text/javascript" src="app.js"></script>

</body>
</html>
```
app.js
```
var app = document.getElementById('app');

console.log(app)
```

#### Пример - document.getElementsByClassName (ES5)
index.html
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

    <div class="articles">

		<div class="article">
			<h2>Здесь будет какой-нибудь заголовок для какой-нибудь записи в каком-нибудь блоге</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
			quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
			cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
			proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		</div>

		<div class="article">
			<h2>Здесь будет какой-нибудь заголовок для какой-нибудь записи в каком-нибудь блоге</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
			quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
			cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
			proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		</div>

		<div class="article">
			<h2>Здесь будет какой-нибудь заголовок для какой-нибудь записи в каком-нибудь блоге</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
			quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
			cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
			proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		</div>

	</div>

    <script type="text/javascript" src="app.js"></script>

</body>
</html>
```
app.js
```
var articles = document.getElementsByClassName('article');

console.log(articles)

console.log(app)
```

#### Для начала рассмотрим разницу между document.getElementById и document.getElementsByClassName.
1. document.getElementById берет элемент из HTML у которого установлен id="somename". Элемент с таким id должен быть уникальным во всей HTML верстке (т.е. он не должен повторяться в HTML коде, т.к. JavaScript не будет понимать с каким именно элементом ему необходимо работать).
2. document.getElementsByClassName имет диаметрально противоположную логику работы: он может обращаться к коллекции элементов с одинаковым классом (т.е. блоков с тэгом class="article", напрмер) и работать уже с коллекцией. Коллекция в данном случае - это, как минимум, 1 элемент с указанным классом.
