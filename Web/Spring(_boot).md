## Spring, Spring boot

### 1. Spring이란?

Java 기반의 web application framework 

- 전체적인 Java 객체들과 라이브러리를 관리합니다.

- 기본적으로 MVC(Model, View, Control)패턴으로 구현됩니다.

- 객체를 통해 데이터를 서로 주고 받거나 접근합니다.

<br><br>

### 2. Spring structure  

![image](https://user-images.githubusercontent.com/70496139/156914546-455e8d6f-eec2-423a-ba3c-cd96e31d8683.png)  

<br><br>

### 3. Sprint boot란?

* Spring과 사용자 사이에 위치하며 사용자가 좀 더 쉽게 Spring을 이용할 수 있도록 도와주는 도구  

* 복잡한 설정들을 간편하게 관리할 수 있도록 해주며, 많은 부분들을 자동화한 도구  

* 현재 대부분의 Spring 개발자는 이를 이용하여 개발함    

<br><br>

### 4. DAO, DTO, VO

다음과 같은 객체들을 통해 데이터를 접근하거나 주고 받습니다.

* DAO(Data Access Object) : DB의 데이터에 접근하기 위한 객체

* DTO(Data Transfer Object) : MVC패턴을 통해 나누어 놓은 계층들간 데이터를 주고 받기 위한 객체

  -> DTO의 적용 범위에 대하여 (View < - > Controller < - > Service < - > Repo)

  * Controller에서 DTO < - > Entity 변환을 하게되는 것이 일반적이나 이 경우 DTO의 재료에 따라  비대해지는 경우가 발생 할 수 있습니다.
  * Service에서 변환을 진행한다면 위의 단점을 해결할 수 있으나, 한 Controller에서 여러  Service를 사용하는 경우 문제가 발생 할  수 있습니다.
  * 해당 프로젝트의 특성에 맞춰 적절하게 협의하여 선택하는 것이 중요하다고 판단됩니다.

* VO(Value Object) : 변하지 않는 고정 값을 지니는 객체

<br><br>  

### 5. Maven과 Gradle

둘 다 기본적으로 빌드 자동화 도구입니다.  
다양한 라이브러리 관리 및 의존성 처리를 간단하게 할 수 있도록 도와줍니다.  

* Maven의 경우 Spring에서 주로 사용됩니다.  
  라이프사이클이라는 미리 정의된 빌드 순서가 있습니다.  

* Gradle의 경우는 Sprintboot와 안드로이드 등에서 사용됩니다.  
  Ant와 Groovy를 기반으로 제작되어 관련 기능들을 모두 사용 가능합니다.  
  Maven과 달리 스크립트를 지원하여 자유로운 로직 구성이 가능합니다.
  시기적으로 Maven보다 늦게 나오며 전체적으로 좋은 성능을 보여줍니다.

<br><br>  

### 6. JDBC와 JPA

JDBC와 JPA는 모두 DB의 데이터를 좀 더 편리하게 처리하기 위한 방식입니다.  
Java의 객체와 DB의 관계를 매핑해주는 ORM(Object-relational mapping)을 기반으로 작동합니다.  
JDBC(Java Database Connectivity)는 기본적으로 자바 API이며 DB접속을 도와줍니다.  
이를 좀 더 쉽게 할 수 있도록 JPA(Java Persistence API)를 사용합니다.  
<img src="https://user-images.githubusercontent.com/70496139/157149518-97fedf4d-0ba9-4155-bf75-e777ab92b44c.png" width="60%"/>

* JPA

  Entity함수에 Column 어노테이션을 사용하여 세부 내용을 작성한 뒤 Repo의 인터페이스에서 해당 Entity를 템플릿으로 사용하여 JPA를 extends 하여 사용한다.  
  전체적으로 많은 부분이 자동화되어 처리해주나 필요한 경우 class로 추가 상속하여 함수들을 오버라이딩 하는 것 또한 가능하다.
  
<br><br>

### 7. Flyway

Entity migration 자동화를 통해 편의성을 도와주는 API입니다.  
정해진 version 파일을 통해 Entity의 변화를 기록하며 수정할 수 있습니다.
