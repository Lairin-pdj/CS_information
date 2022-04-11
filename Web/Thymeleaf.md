## Thymeleaf (타임리프)

### 1. Thymeleaf (타임리프)에 대해서

Thymeleaf는 View Template의 일종으로 컨트롤러가 보내주는 동적인 모델을 매핑하여 보여주는 역할을 합니다.

<br>


### 2. 프로젝트 적용법

gradle 파일에 해당 의존성을 추가하면 사용할 수 있습니다.

```gradle
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
}
```

<br>


### 3. 사용방법

첫번째로 Controller에서 모델에 해당하는 attributename을 지정하여 전송해줍니다.

```java
@GetMapping("/")
public String list(Model model) {
    List<WebpageDto> webpageList = webpageService.getWebpagelist();

    model.addAttribute("webpageList", webpageList);
    return "webpage/list.html";
}
```

 그 후 return을 통해 호출되는 페이지에서  xmlns를 통해 포함시킨뒤 attributename을 이용하여 매핑된 데이터를 사용할 수 있습니다.

```html
<html lang="en" xmlns:th="http://www.w3.org/1999/xhtml">
	<thead>
         <tr>
             <th class="one wide">번호</th>
             <th class="ten wide">글제목</th>
             <th class="two wide">작성자</th>
             <th class="three wide">작성일</th>
         </tr>
    </thead>

    <tbody>
        <tr th:each="webpage : ${webpageList}">
            <td>
                <span th:text="${webpage.id}"></span>
            </td>
            <td>
                <a th:href="@{'/post/' + ${webpage.id}}">
                    <span th:text="${webpage.title}"></span>
                </a>
            </td>
            <td>
                <span th:text="${webpage.writer}"></span>
            </td>
            <td>
                <span th:text="${#temporals.format(webpage.createdDate, 'yyyy-MM-dd HH:mm')}"></span>
            </td>
        </tr>
    </tbody>
</html>
```

<br>


### 4. 문법

전체적으로 th:{op}="${variable}"과 같은 형태로 구성합니다.

* th:each 

  >반복문의 역할을 합니다.
  >
  >위 예시의 th:each="webpage : ${webpageList}" 처럼 사용할 수 있습니다.

* th:text

  > html 문서내에서 주어진 변수등을 텍스트처럼 인식하게 해줍니다.

* th:href

  > 해당 블록에 주어진 주소로 하이퍼링크를 걸어줍니다.

* th:onclick

  > 클릭시 해당하는 함수가 호출됩니다.

* th:attributename

  > 주어진 이름의 변수를 생성합니다.
  >
  > 이는 this.getAttribute('attributename')의 형태로 호출할 수 있습니다.

* th:if, th:unless 

  >조건분기가 가능합니다.
  >
  >```html
  ><p th:if="${target}=='True'" th:text="True"></p>
  ><p th:unless="False"></p>
  >```
  
* th:replace, th:insert, th:include

  >모두 특정 코드를 붙여주는 문법이면서 각 문법마다 약간의 특색이 존재한다.
  >
  >```html
  ><footer th:fragment="copy">
  >  	&copy; 2011 The Good Thymes Virtual Grocery
  ></footer>
  >```
  >
  >```html
  ><body>
  >  	<div th:insert="footer :: copy"></div>
  >  	<div th:replace="footer :: copy"></div>
  >  	<div th:include="footer :: copy"></div>
  ></body>
  >```
  >
  >```html
  ><body>
  >    	<!-- insert -->
  >    	<div>
  >    		<footer>
  >      			&copy; 2011 The Good Thymes Virtual Grocery
  >    		</footer>
  >  	</div>
  >    
  >    	<!-- replace -->
  >  	<footer>
  >    		&copy; 2011 The Good Thymes Virtual Grocery
  >  	</footer>
  >    
  >    	<!-- include -->
  >  	<div>
  >    		&copy; 2011 The Good Thymes Virtual Grocery
  >  	</div>
  ></body>
  >```

* th:fragment

  > 공통 부분을 fragment로 생성하여 대체하는 문법
  >
  > ```html
  > <!-- 파라미터를 통해 값을 전달 받아 생성자처럼 작동함  -->
  > <!-- th:with를 사용하여 고정 파라미터 외의 다른 파라미터를 받을 수 있다.  -->
  > <!-- th:id와 class를 이용하여 id와 class를 추가로 설정 할 수 있다.  -->
  > <div th:fragment="fragment(id)"
  >       th:with="content=(${ content } ?: null), script=(${ script } ?: false)"
  >       class="add-class"
  >       th:id="${ id }">
  >     <div class="content" th:if="${content != null}">
  >         <th:block th:replace="${content}"></th:block>
  >     </div>
  >     <script defer th:if="${script}" th:inline="javascript">
  >         /* script */
  >     </script>
  > </div>
  > ```
