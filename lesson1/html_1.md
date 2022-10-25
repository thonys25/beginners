# 1. Основы HTML
[![test](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

### 1.1 Базовая разметка
Чтобы создать базовую разметку в [Sublime Text 3](https://www.sublimetext.com/3), необходимо в правом нижнем углу поменять Plain Text на HTML, после чего написать html и нажать Tab. В итоге должна получиться следующая разметка:

#### Базовая разметка

```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>

</body>
</html>
```

### 1.2 Добавление стилей
Добавить стили можно двумя способами:

#### Первый вариант: добавить тег <style\> перед закрывающим тегом </head\>

```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<style>
/*Какой-то код*/
</style>
<body>

</body>
</html>
```

#### Второй вариант: добавить тег <link\> после тэга <title\>
В этом случае вам понадобится создать файл styles.css (файл может называться как угодно, но обычно его называют либо styles.css, либо style.css

```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

</body>
</html>
```

### 1.3 Блочная верстка
Верстка бывает двух типов: табличная и блочная. Если раньше верстали сайты, используя табличную верстку, то сейчас верстают, используя блочную верстку. Блочная верстка - это, по-большей своей части, всегда DIV. Для простоты понимания, будет называть это контейнером, который может хранить в себе: изображения, видео, элементы управления в виде кнопок, поле для ввода и другие контейнеры (по-аналогии с матрешками).

#### Пример контейнера (div блока), который содержит изображение
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>

    <div class="myblock">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
    </div>

</body>
</html>
```

#### По такому же принципу контейнер (div блок) может содержать внутри себя другой контейнер (или несколько контейнеров)
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>
    
    <div class="header">
    
        <div class="logo">
            <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
        </div>
        
        <div class="sitename">
            <p>Название сайта</p>
        </div>
        
        <div class="profile">
            <a href="#">Мой аккаунт</a>
        </div>
    </div>
    
    <div class="content">
        <p>Здесь будет основной контент</p>
    </div>

</body>
</html>
```
В данном случае мы создали два блока:
1. Блок с классом header, который будет отображаться у нас в самом верху страницы и который содержит внутри себя ещё три блока: logo (логотип нашего сайт), sitename (название сайта) и profile (ссылка-заглушка).

2. Блок с классом content в котором у нас будет отображаться какой-то контент (например, статьи, как в блоге или просто какой-то текст, как в нашем случае)

Блок со статьями, например, выглядел бы следующим образом:
```
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<link rel="stylesheet" type="text/css" href="styles.css" />
</head>
<body>
    
    <div class="header">
    
        <div class="logo">
            <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg">
        </div>
        
        <div class="sitename">
            <p>Название сайта</p>
        </div>
        
        <div class="profile">
            <a href="#">Мой аккаунт</a>
        </div>
    </div>
    
    <div class="content">
    
        <div class="article">
            <h2>Заголовок статьи</h2>
            <p>Текст статьи</p>
        </div>
        
        <div class="article">
            <h2>Заголовок статьи</h2>
            <p>Текст статьи</p>
        </div>
        
        <div class="article">
            <h2>Заголовок статьи</h2>
            <p>Текст статьи</p>
        </div>
        
        <div class="article">
            <h2>Заголовок статьи</h2>
            <p>Текст статьи</p>
        </div>
        
        <div class="article">
            <h2>Заголовок статьи</h2>
            <p>Текст статьи</p>
        </div>
        
    </div>

</body>
</html>
```

Как можно заметить, мы просто продублировали блок article внутри блока content 5 раз, создав таким образом 5 статей с одинаковым заголовком и описанием.

### 1.3 Подсказки
1. Тэг <p\> - это параграф (иначе говоря - обычный текст без какого-либо начертания). Его используют повсеместно за исключением тех мест, где нужен, например, жирный шрифт.
2.Тэг <h2\> - это header (иначе говоря - заголовок с индексом 2). Обычно используется для заголовков (например, заголовок статьи или новая глава в книге выделяются жирным шрифтом формата h2. Заголовки бывают от h1 до h6 (от самого жирного до самого худого)