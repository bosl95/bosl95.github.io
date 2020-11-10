---
layout: post
title: "Spring Date For Spring Day (1)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot과 친해지기 (1)

# Spring boot의 의미란 무엇인가?

스프링 부트에 들어가기 앞서, 오랜 기간 동안 작성하게 될 이 시리즈의 제목을 잘 정하고 싶어 고민하던 찰나에 스프링 부트 어원에 대한 궁금증이 생겼다.<br>
스프링 부트의 "스프링"은 기존 [EJB](https://ko.wikipedia.org/wiki/%EC%97%94%ED%84%B0%ED%94%84%EB%9D%BC%EC%9D%B4%EC%A6%88_%EC%9E%90%EB%B0%94%EB%B9%88%EC%A6%88)로 대표되는 Enterprise Framework의 시대를 겨울(winter)로 정의하고 이제 **봄**(Spring)이 왔다는 의미로 지어졌다고 한다.<br>
그렇다면 부트는 무엇일까? [이 글](https://stackoverflow.com/questions/60219008/what-is-the-meaning-of-boot-in-spring-boot-title)을 통해 "부트"의 의미를 알 수 있었다.<br>
스프링은 자바의 프레임 워크인데, 스프링을 bootstrapping한 것이 스프링 부트라고 한다.<br>
<br>

![image](https://user-images.githubusercontent.com/34594339/98670344-ee4c2900-2395-11eb-9be4-10477825485c.png)

<br>

전혀 와닿질 않아 다른 블로그들의 정보를 더 찾아보았다.<br>

> - `Spring Framework` : 개발자가 비즈니스 로직에 집중할 수 있도록, JAVA 기반 엔터프라이즈 애플리케이션을 위한 종합적인 기능을 지원하는 프레임워크<br>
>   - 기업용(엔터프라이즈) 애플리케이션 : 대규모 데이터 처리와 트랜잭션이 동시에 여러 사용자로부터 행해지는 매우 큰 규모의 환경을 엔터프라이즈 환경이라고 말한다.<br>
>   - Spring을 통해 기업용 애플리케이션을 만드는 이유? DI, IoC를 통해 재사용 및 유지보수가 용이한 코드 작성이 가능하고 확장성을 가진 코드로 설계할 수 있다. 뿐만아니라 스프링이 제공해주는 기능들을 통해 개발자는 비즈니스 로직에만 집중할 수 있기때문에 생산성을 증가 시킬 수 있다. 
> - `Spring boot` : 스프링 기반 애플리케이션을 쉽게 만들 수 있다. 즉, 스프링을 쉽게 사용할 수 있도록 필요한 설정을 대부분 미리 세팅해놓았다는 뜻이다. <br>

<br>

아무튼 Spring과 데이트(?)하면서 Spring day가 올 때까지 도전하겠다는 나름의 의미를 담아 제목을 지어봤다.<br>

<br>

# Spring boot를 왜 사용하는가?

Spring boot 외에도 Java 웹 어플리케이션을 만들 수 있다(고 한다. 잘 몰라서 찾아보니 스트럿츠라는 MVC 모델2에 기반한 프레임워크가 있다고 한다.) <br>
그렇다면 스프링 부트로 개발하는 이유가 무엇일까?<br>

1. 서버를 구축하는 데 간편하다.
   - 과거 스프링 MVC 프레임워크를 사용할 때는 Tomcat 라이브러리를 다운받아 경로를 확인하고 import 해준 뒤 설정해야하는 번거로움이 있었다고 한다.
   - 스프링부트에서는 웹서버 tomcat이 내장되어 있어 따로 설정하지 않아도 서버를 실행할 수 있다.
2. 수 많은 스프링 프레임워크가 한 곳에 모여있다.
   - 스프링부트 프레임워크는 spring data, spring web service, spring mobile, spring mvc 등 다양한 스프링 프레임워크를 마우스 클릭 몇번으로 가져와 사용할 수 있다.
   - 다양하고 유용한 라이브러리들을 쉽게 가져와서 활용할 수 있다는 것이다.
3. 가볍고 쉽다. 
   - Spring MVC 프레임워크를 사용할 때는 여러 xml 파일을 작성해야하는 어려움도 있었고 굉장히 무거웠다고 한다.
   - 하지만 스프링 부트는 설정 파일을 작성하는데 투자한 시간을 개발에 투자할 수 있도록 설정 파일 작성을 할 필요가 없다.
  
 <br>
 
 
# Web Application Server란 무엇인가?
 
 웹 어플리케이션이 배포되는 공간을 뜻한다.<br>
 HTML과 같은 정적 파일들을 전달해주는 역할을 하는 서버를 **웹 서버**라고 하고, PHP, JSP, ASP와 같은 언어들을 사용해 동적 페이지 생성이 가능한 서버를 웹 애플리케이션 서버(Web Application Server) 혹은 웹 어플리케이션 컨테이너(WAS)라고 한다.<br>
 
 <br>
 
## Class Loader
자바 코드를 작성한 후 컴파일하면 해당 코드는 JVM(Java Virtual Machine)에서 실행 가능한 상태가 된다.<br>
이때 JVM이 클래스를 실행하기 위해서 클래스를 로딩하는 과정이 필요하다. 그 과정을 수행해주는 역할이 **Class Loader**이다.<br> 
다른 사람의 프로젝트를 로컬에서 실행하거나 새로운 프레임워크를 테스트해볼 때 ClassNotFoundException과 같은 에러를 만난다. 이 에러는 Class loader가 추가된 라이브러리 또는 클래스를 인식하지 못해 발생하는 오류이다.<br>
클래스패스(class path)에 해당 모듈 또는 라이브러리를 추가하면 오류는 사라진다.<br>

- 클래스 로더의 특징

  1. 구조가 계층적이다.
  2. 클래스 로딩을 위임할 수 있다.
  3. 가시적인 규약이 있다. (클래스를 로딩할 떄 가능한 범위가 있다. 자식 클래스 로더는 클래스 로딩 요청 위임을 통해 부모 클래스 로더가 로딩한 클래스를 찾을 수 있지만, 부모 클래스 로더는 자식 클래스 로더가 로딩한 클래스를 알 수 없다. ~~자식 이기는 부모 없다고..~~)<br>
  4. 클래스 언로딩이 불가능하다. 클래스 로더로 로딩한 클래스들을 언로딩 할 수 없다. 가비지 컬렉터가 동작하거나 WAS가 재시작할 때 초기화 된다.

![image](https://user-images.githubusercontent.com/34594339/98675313-6ec25800-239d-11eb-8a10-0241d02c45df.png)

<br>

- 클래스 로더의 유형
   - 부트스트랩 클래스 로더 : JVM 런타임 실행을 위해 기반이 되는 파일들을 로드. rt.jar 파일과 연관이 있다.
   - 확장 클래스 로더 : 부트스트랩 클래스 로더가 끝나면 자바의 최상위 객체인 Object를 포함한 자바 API를 로드한다. (자바 홈 폴더 하위의 ext 폴더 하위에 있는 jar 파일들과 연관이 있다.)
   - 시스템 클래스 로더 : 클래스패스에 포함된 클래스들을 로드한다.

<br>

![image](https://user-images.githubusercontent.com/34594339/98675719-fad47f80-239d-11eb-94f5-3268d19f3349.png')

<br>

# WAR과 JAR

둘 다 JAVA의 jar 툴을 이용하여 생성된 압축(아카이브) 파일이며, 어플리케이션을 쉽게 배포하고 동작시킬 수 있도록 관련 파일(리소스, 속성 파일 등)을 패키징해주는 것이 주역할이다.<br>

- JAR(Java Archive) : 여러 개의 자바 클래스 파일과 클래스들이 사용하는 관련 리소스 및 메타 데이터를 하나의 파일로 모아 자바 플랫폼에 응용 sw나 라이브러리를 배포하기 위한 sw 패키지 파일 포맷
- WAR(Web Application Archive) : servlet/jsp 컨테이너에 배치할 수 있는 웹 어플리케이션 압축 파일 포맷.
    - JSP,  SERVLET, JAR, CLASS, XML, HTML, JAVASCRIPT 등  Servlet Context 관련 파일들로 패키징되어 있다.
    - 웹  관련 자원만 포함하고 있으며 이를 사용하면 웹 어플리케이션을 쉽게 배포하고 테스트할 수 있다.
    - 웹 어플리케이션 컨테이너는 WAR 파일의 WEB-INF 폴더를 기준드로 클래스 파일들을 로드한다.
    - WAR로 패키징하면 클래스 파일들은 WEB-INF 하위 classses 폴더에 저장된다.

<br>

![image](https://lh6.googleusercontent.com/u9wIjJo3mGFI3OtTQsMbE-KfgcwaDkXYk5Oag2jWkoMArFLJeQhPtzCuTV-QL8TOjff8iX750gZWSuNSyqy8LMLtBSZgs9QWUDlLYI9sJb_6NyjwtkvW1XFlQevusKVOOEkvSnFd)

<br>

# 참고

- [spring과 springboot 차이를 그림으로 보고 싶으시다면 추천(자세한 내용을 모르신다면 패스)](https://ssoco.tistory.com/66)
- [Spring이란 무엇인가 Spring boot란 무엇인가](https://noahlogs.tistory.com/46)
- [WAR과 JAR](https://taewooblog.tistory.com/111)

