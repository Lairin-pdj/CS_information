## Spring, Spring boot

### 1. Spring이란?
Java 기반의 web application framework 
- 전체적인 Java 객체들과 라이브러리를 관리합니다.
- 기본적으로 MVC(Model, View, Control)패턴으로 구현됩니다.
- 객체를 통해 데이터를 서로 주고 받거나 접근합니다.
  
- Spring structure  

![image](https://user-images.githubusercontent.com/70496139/156914546-455e8d6f-eec2-423a-ba3c-cd96e31d8683.png)  
  
  
### 2. Sprint boot란?
* Spring과 사용자 사이에 위치하며 사용자가 좀 더 쉽게 Spring을 이용할 수 있도록 도와주는 도구  
* 복잡한 설정들을 간편하게 관리할 수 있도록 해주며, 많은 부분들을 자동화한 도구  
* 현재 대부분의 Spring 개발자는 이를 이용하여 개발함    
  
  
### 3. DAO, DTO, VO
다음과 같은 객체들을 통해 데이터를 접근하거나 주고 받습니다.
* DAO(Data Access Object) : DB의 데이터에 접근하기 위한 객체
* DTO(Data Transfer Object) : MVC패턴을 통해 나누어 놓은 계층들간 데이터를 주고 받기 위한 객체
* VO(Value Object) : 변하지 않는 고정 값을 지니는 객체
