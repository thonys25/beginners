# 1. ������ HTML
[![test](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

### 1.1 ������� ��������
����� ������� ������� �������� � [Sublime Text 3](https://www.sublimetext.com/3), ���������� � ������ ������ ���� �������� Plain Text �� HTML, ����� ���� �������� html � ������ Tab. � ����� ������ ���������� ��������� ��������:

#### ������� ��������

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

### 1.2 ���������� ������
�������� ����� ����� ����� ���������:

#### ������ �������: �������� ��� <style\> ����� ����������� ����� </head\>

```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<style>
/*�����-�� ���*/
</style>
<body>

</body>
</html>
```

#### ������ �������: �������� ��� <link\> ����� ���� <title\>
� ���� ������ ��� ����������� ������� ���� styles.css (���� ����� ���������� ��� ������, �� ������ ��� �������� ���� styles.css, ���� style.css

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

### 1.3 ������� �������
������� ������ ���� �����: ��������� � �������. ���� ������ �������� �����, ��������� ��������� �������, �� ������ ��������, ��������� ������� �������. ������� ������� - ���, ��-������� ����� �����, ������ DIV. ��� �������� ���������, ����� �������� ��� �����������, ������� ����� ������� � ����: �����������, �����, �������� ���������� � ���� ������, ���� ��� ����� � ������ ���������� (��-�������� � ����������).

#### ������ ���������� (div �����), ������� �������� �����������
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

#### �� ������ �� �������� ��������� (div ����) ����� ��������� ������ ���� ������ ��������� (��� ��������� �����������)
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
            <p>�������� �����</p>
        </div>
        
        <div class="profile">
            <a href="#">��� �������</a>
        </div>
    </div>
    
    <div class="content">
        <p>����� ����� �������� �������</p>
    </div>

</body>
</html>
```
� ������ ������ �� ������� ��� �����:
1. ���� � ������� header, ������� ����� ������������ � ��� � ����� ����� �������� � ������� �������� ������ ���� ��� ��� �����: logo (������� ������ ����), sitename (�������� �����) � profile (������-��������).

2. ���� � ������� content � ������� � ��� ����� ������������ �����-�� ������� (��������, ������, ��� � ����� ��� ������ �����-�� �����, ��� � ����� ������)

���� �� ��������, ��������, �������� �� ��������� �������:
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
            <p>�������� �����</p>
        </div>
        
        <div class="profile">
            <a href="#">��� �������</a>
        </div>
    </div>
    
    <div class="content">
    
        <div class="article">
            <h2>��������� ������</h2>
            <p>����� ������</p>
        </div>
        
        <div class="article">
            <h2>��������� ������</h2>
            <p>����� ������</p>
        </div>
        
        <div class="article">
            <h2>��������� ������</h2>
            <p>����� ������</p>
        </div>
        
        <div class="article">
            <h2>��������� ������</h2>
            <p>����� ������</p>
        </div>
        
        <div class="article">
            <h2>��������� ������</h2>
            <p>����� ������</p>
        </div>
        
    </div>

</body>
</html>
```

��� ����� ��������, �� ������ �������������� ���� article ������ ����� content 5 ���, ������ ����� ������� 5 ������ � ���������� ���������� � ���������.

### 1.3 ���������
1. ��� <p\> - ��� �������� (����� ������ - ������� ����� ��� ������-���� ����������). ��� ���������� ����������� �� ����������� ��� ����, ��� �����, ��������, ������ �����.
2.��� <h2\> - ��� header (����� ������ - ��������� � �������� 2). ������ ������������ ��� ���������� (��������, ��������� ������ ��� ����� ����� � ����� ���������� ������ ������� ������� h2. ��������� ������ �� h1 �� h6 (�� ������ ������� �� ������ ������)