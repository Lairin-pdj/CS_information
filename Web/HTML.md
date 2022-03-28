## HTML(Hypertext Markup Language)
웹 페이지의 모습을 기술하기 위한 규약으로 프로그래밍 언어가 아닌 마크업 언어입니다.

<br>

### 1. 형태 및 구조
기본적인 형태는 다음과 같습니다.  
```html
<tag>내용</tag>
<tag attribute1="value1" attribute2="value2">내용</tag>
```
위와 같이 태그를 사이에 두고 내용을 넣으며 태그에 속성을 지정할 수 있습니다.    
기본적인 구조는 다음과 같습니다.
```html
<!DOCTYPE HTML>
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        example
    </body>
</html>
```
전체적으로 html 태그로 감싸며 head와 body를 분리하여 작성합니다.

<br>

### 2. 태그
* head
* meta
* title
* link
* body
* span, a, h(n)
* div
* table
* input
* output
* form
* button
* dialog
* script

<br>

### 3. 옵션
* onclick
* style
* id
* class
* type
* name

<br>

### 4. xmlns

XML namespace의 줄임말로 XML요소 간의 충돌을 막아주는 기능을 합니다.   
```html
<html lang="en" xmlns:th="http://www.w3.org/1999/xhtml">
```

```html
<html lang="ko" xmlns:th="http://www.thymeleaf.org">
```

위와 같은 형태로 설정할 수 있으며 해당하는 네임스페이스의 다양한 기능을 가져와 사용하는 것이 가능합니다.
