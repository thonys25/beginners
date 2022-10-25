# 2. Основы CSS
[![test](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

### 2.1 Базовая CSS разметка
Для того, чтобы начать писать стили для HTML блоков нам нужно убрать отступы (сверху и слева). Для этого мы обращаемся ко всем элементам на стринце с помощью \*.

#### Убираем отступы

```
* {
    padding: 0; /* Убираем внутренние отступы */
    margin: 0;  /* Убираем внешние отступы */
}
```
После того, как мы убрали отступы, можно приступить к оформление отдельных блоков. Изначально, если блок находится между тэгами <body\></body\>, то он, как правило, не имеет ни ширины, ни высоты, ни фонового цвета, вообще ничего.

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

    <div class="block"></div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
```
Однако, если поместить внутрь блока, например, картинку, то он растянется по ширине и высоте содержимого (т.е. нашей картинки) или на всю страницу, как в нашем случае.

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

    <div class="block">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
```
В таком случае, можно подумать, что достаточно уменьшить размер нашего блока с классом .block, чтобы картинка стала меньше и помещалась в него. Например, следующим образом.

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

    <div class="block">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
.block {
    width: 250px;
    height: 250px;
}
```
Однако на деле это не сработает, т.к. картинка имеет размеры в значительной степени больше, нежели наш блок и тот факт, что она находится внутри блока, не делает её зависимой от блока (и её размеров соответственно). Исправить эту ситуацию можно двумя путями.

#### 1. Сделать картинку зависимой от блока
Это решение является правильным, т.к. картинка не должна вылезать за границы блока в котором она находится (как, собственно и любой другой элемент). Иная ситуация может использоваться, например, если у блока имеется свойство overflow: hidden.

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

    <div class="block">
        <img class="logo" src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
.block {
    width: 250px;
    height: 250px;
}
.logo {
    width: 100%;
}
```

#### 2. Установить фиксированное значение картинки (или динамическое в процентном соотношении)
Не всегда разумное решение, т.к. на разных устройствах (и, следовательно, на разных дисплеях) разное соотношение сторон (диагональ) и разная плотность пикселей, что может приводить к тому, что элемент (картинка, например) будет вылезать за границы отведённого ей блока.

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

    <div class="block">
        <img class="logo" src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
.block {
    width: 250px;
    height: 250px;
}
.logo {
    width: 150px;
}
```

#### 3. Комбинирование подходов
Иногда комбинируют два предыдущих подхода, чтобы при изменении экрана размер картинки становился меньше.

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

    <div class="block">
        <img class="logo" src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
.block {
    width: 250px;
    height: 250px;
}
.logo {
    max-width: 200px;
    width: 100%;
}
```

### 2.3 Позиционирование элементов
Зачастую нам приходится позиционировать наши контейнеры (div блоки) и содержимое внутри наших контейнеров. Так, например, чтобы создать контейнер, который будет содержать список статей, нам нужно сделать ему отступы по краям (слева и справа). Для наглядности попробуйте прочитать содержимое на такой странице

#### Плохой пример
Читать текст на такой странице - это настоящее испытание себя. Если вы не Wikipedia, то ваш сайт с такой версткой едва ли кому-нибудь приглянется (будет по-душе).

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
			<h2 class="title">Здесь будет какой-нибудь заголовок для какой-нибудь записи в каком-нибудь блоге</h2>
			<p class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
			quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
			cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
			proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		</div>
	</div>

</body>
</html>
```
styles.css
```
* {
    padding: 0;
    margin: 0;
}
.title {
    line-height: 26px;
    margin-bottom: 15px;
}
.description {
    line-height: 22px;
}
```

#### Хороший пример
Установить блоку максимальную ширину (допустим, 450px), чтобы пользователю было удобно читать такой текст.

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
			<h2 class="title">Здесь будет какой-нибудь заголовок для какой-нибудь записи в каком-нибудь блоге</h2>
			<p class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
			quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
			cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
			proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		</div>
	</div>

</body>
</html>
```
styles.css
```
* {
	padding: 0;
	margin: 0;
}
.articles {
	max-width: 450px;
	width: 100%;
}
.article {
    width: 95%;
    margin: 0 auto;
}
.title {
    line-height: 26px;
    margin-bottom: 15px;
}
.description {
    line-height: 22px;
}
```

1. Здесь мы задали максимальную ширину нашему основному контейнеру (div блоку) с классом .articles ширину в 450px (т.е. шире 450 пикселей он быть не может)

2. Для блока с классом .article мы задали ширину в 95% от родительского блока с классом .articles и с помощью margin: 0 auto выровняли его по центру, сделав таким образом отступы по краям.