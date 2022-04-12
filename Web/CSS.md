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

중복되는 값을 막거나 전체적인 적용을 한번에 하기위해 변수가 사용 가능합니다.  
변수의 경우 기본적인 css 문법의 유효값에 "--"를 앞에 붙여 사용합니다.   
그 값을 var()을 통해 불러올 수 있습니다.

```html
:root {
  --main-bg-color: brown;
}

element {
  background-color: var(--main-bg-color);
}
```

<br>

### 3. 의사 클래스

css에서 :를 통해 뒤에 덧붙여주는 클래스이며, 좀 더 세분화된 조정을 가능케합니다.

```css
button:hover {
  color: blue;
}
```

hover, checked, active, root, visited 등 굉장히 다양한 의사 클래스가 존재하며 이를 이용하여 특정 상황에 모양을 바꾸어주는 것이 가능합니다.

[참고자료-pseudo class](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes)

<br>

### 4. 유용한 속성 정리

* flex

  > 빈 공간을 알아서 자동으로 채워주는 유용한 display 중 하나입니다.
  >
  > - flex_direction : 순서의 방향을 지정합니다.
  >
  > - justify-content : 좌우 정렬의 기준선을 지정합니다.
  >
  > - align-content : 상하 정렬의 기준선을 지정합니다.
  >
  > - align-items : 상하 정렬을 지정합니다.
  >
  > [참고자료-flex](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)

* grid

  > 2차원 배열의 형태로 자리를 잡고 엑셀처럼 공간을 할당해주는 방식으로 UI를 꾸밀 수 있는 방법입니다.
  >
  > 자식 div들을 column과 row를 사용하여 좌표로 지정가능하며, 이를 통해 중첩 grid를 사용하거나 grid의 div끼리도 겹칠 수 있습니다. 
  >
  > fr을 이용해 weight를 설정해줄 수도 있으며, repeat와 auto-fit, auto-fill을 통해 자동반복 또한 가능합니다.
  >
  > [참고자료-grid](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Grid_Layout/Basic_concepts_of_grid_layout)

