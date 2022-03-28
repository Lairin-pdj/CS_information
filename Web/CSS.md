## CSS(Cascading Style Sheets)

### 1. CSS란

CSS는 HTML이나 XML, XHTML로 작성된 문서의 표시 방법을 기술하기 위한 스타일 시트 언어입니다.   
주로 HTML의 위치, 모양, 형식 등을 정의하며, 애니메이션 효과 등 단조로운 문서를 다채롭게 바꾸어주는 역할을 담당합니다. 

<br>

### 2. 문법 및 사용법

CSS를 HTML에 적용하는 방법은 두가지가 있습니다.  
그 중 첫번째는 HTML 문서에서 원하는 태그에 직접 style을 기입하는 방법입니다.  
```html
<div class="main" style="display: flex">
```
위와 같은 방식으로  다양한 속성을 부여할 수 있습니다.

두번째 방법은 별도로 CSS 파일을 생성하여 작성하는 방법입니다.

```html
 <link rel="stylesheet" href="/css/main.css">
```

먼저 위와 같이 HTML에 헤더에서 해당하는 문서를 연결해줍니다.

그 후 아래와 같은 문법으로 작성하여 적용합니다.

```css
/* 주석 */

/* 클래스 */
.class {	
    atrribute: value;
    ...
}

/* id */
#id {	
    atrribute: value;
    ...
}
```

<br>

### 3. 유용한 속성 정리

* flex

  > 빈 공간을 알아서 자동으로 채워주는 유용한 display 중 하나입니다.
  >
  > - flex_direction : 순서의 방향을 지정합니다.
  > - justify-content : 좌우 정렬의 기준선을 지정합니다.
  > - align-content : 상하 정렬의 기준선을 지정합니다.
  > - align-items : 상하 정렬을 지정합니다.