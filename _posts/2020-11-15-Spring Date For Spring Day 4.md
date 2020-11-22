---
layout: post
title: "Spring Date For Spring Day (4)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot 네번째<br>
<br>

- 이전 글 : [Spring Date For Spring Day (3)](https://bosl95.github.io/Spring-Date-For-Spring-Day-3/)

# Spring DI 지시서 작성하기(Spring Bean Configuration)

우선 setExam() 함수를 만들어봅시다. 밑의 create를 누르면 자동으로 ExamConsole에 setExam()이 생성됩니다.<br>
(여기서 GridExamConsole안에 매개변수가 있는데, 뒤에서 삭제됩니다.)<br>

![image](https://user-images.githubusercontent.com/34594339/99187483-3a360e00-279a-11eb-8fbf-d1c7c6e471f0.png)

- 그리고 에러가 나는 ExamConsole 클래스들에 마우스를 갖다대면 자동으로 Add할 수 있는 가이드가 뜹니다. 그것을 클릭하여 함수들을 생성하여 줍시다.

생성된 setExam() 함수에는 이렇게 설정해주었습니다.<br>

![image](https://user-images.githubusercontent.com/34594339/99187554-a153c280-279a-11eb-840e-d912b507ef2c.png)

매개변수가 없는 생성자를 각 ExamConsole 클래스들에 컨트롤+스페이스를 이용하여 생성해줍시다.<br>

자, 이렇게 set을 이용하여 DI를 만들어 주었습니다.<br>

![image](https://user-images.githubusercontent.com/34594339/99187689-73bb4900-279b-11eb-89d2-ea1bba6b8fea.png)

그러면 이제 스프링에게 지시하는 방법으로 저 코드들을 변경해보려고 합니다.<br>

![image](https://user-images.githubusercontent.com/34594339/99187823-2e4b4b80-279c-11eb-83c9-3c3416115b84.png)

이 부분의 코드를 스프링 지시서인 setting.xml에서 작성해봅시다.<br>

- setting.xml


      <?xml version="1.0" encoding="UTF-8"?>
      <beans xmlns="http://www.springframework.org/schema/beans"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
        <bean id="exam" class="spring.di.entity.NewExam"></bean>      // Exam exam = new NewExam();와 같은 의미

      </beans>

이때 id는 설정해준 이름인 exam을, class는 new로 초기화 해주었던 NewExam을 썼습니다.(이름 중복을 방지하기 위해 패키지명도 합께 입력해줍니다)<br>

<br>

그렇다면 console.setExam()은 어떻게 설정해줄까요?<br>

      <bean id="console" class="spring.di.ui.newGridExamConsole">
        <property name="exam" ref="exam" />
      </bean>


set은 묵시적으로 생략 가능하고 대문자는 소문자로 바꿔줍니다. name안에 들어간 exam은 setExam()을 부르는 것을 의미합니다. (매개변수 exam이 아닙니다.)<br>
매개변수는 value나 ref를 이용해서 값을 전달해줄 수 있는데 이 경우 객체를 전달해주므로 ref를 사용합니다.<br>

<br>

# Application Context

Applicationcontext를 통해 xml 파일을 읽어올 수 있습니다.<br>
Applicationcontext는 지시서의 위치에 따라 종류가 나뉩니다.<br>

- ### ApplicationContext의 종류
  - ClassPathXmlApplicationContext : 어플리케이션 루트에 있는 경우. 가장 보편적이다.
  - FileSystemXmlApplicationContext : C드라이브의 한 곳에 있다.
  - XmlWebApplicationContext  : 웹에 있는 경우
  - AnnotationConfigApplicationContext : 스캔하는 방법을 쓴다.(뒤에서 설명)
  
<br>

Applicationcontext를 사용하기 위해서는 스프링라이브러리를 가져와야합니다.<br>
스프링 라이브러리를 가져오는 방법에는 1. 스프링 라이브러리 직접 다운로드 2. 메이븐 프로젝트라면 dependency를 지정해주면 알아서 가져오는 2가지 방법이 있습니다.<br>
메이븐 프로젝트로 바꾸어 스프링 라이브러리를 가져오도록 하겠습니다.<br>

<br>


# ApplicationContext를 통해 지시서 사용하기

  ![image](https://user-images.githubusercontent.com/34594339/99906750-23546600-2d1c-11eb-85f3-e94f7f39aaf4.png)
  ![image](https://user-images.githubusercontent.com/34594339/99907673-7d0b5f00-2d21-11eb-8b91-c1ce1f4a4b79.png)
  ![image](https://user-images.githubusercontent.com/34594339/99907687-8c8aa800-2d21-11eb-862b-33badfc1f23d.png)

  이렇게 pom.xml 파일이 하나 생성되었습니다.<br>

<br>

- Maven 인덱스를 추가하여 Dependency 추가할 때 검색 가능하도록 해주겠습니다.
  
  ![image](https://user-images.githubusercontent.com/34594339/99907883-c60fe300-2d22-11eb-88d9-cf525f2af1dc.png)

  others를 눌러 Maven Repositories를 클릭합시다<br>
  
  ![image](https://user-images.githubusercontent.com/34594339/99907959-1129f600-2d23-11eb-835a-41eaef0aa938.png)
   
  Rebuild index를 눌러 메이븐 인덱스를 불러옵니다.<br>
  
- Dependency 추가하기

  ![image](https://user-images.githubusercontent.com/34594339/99907733-c6f44500-2d21-11eb-9b90-8bc8cceb1960.png)

  하단의 Dependecies를 눌러서 하나 추가해줍시다.<br>
   
<br>

- 시간이 오래 걸리므로 직접 다운로드하는 방법으로 설명하자면, 

  1. [메이븐 레포지토리 사이트](https://mvnrepository.com/)에 들어갑니다.
  2. "Spring Framework"를 검색하여 줍니다.
  3. Spring Context를 클릭하고 기호에 맞는 버전을 선택하여 메이븐 태그의 코드를 클릭하여 복사해줍니다.
  4. pom.xml 파일에 <version> 태그 바로 밑에 <dependencies>를 만들어 그 안에 복사한 코드를 넣어줍니다.
  5. depency hierachy를 들어가보면 spring context가 추가된 것을 볼 수 있습니다.(필요한 라이브러리를 자동 추가된 것을 볼 수 있습니다.)
      
     ![image](https://user-images.githubusercontent.com/34594339/99908974-0e320400-2d29-11eb-993f-83890878fa68.png)
  
  6. 이제 ApplicationContext를 자동 import 하면 됩니다!!!! 👏🏻👏🏻👏🏻👏🏻 (만약 클릭이 안되는 경우 프로젝트 우클릭 > 메이븐 > update project를 하면 import가 가능합니다)

<br>

# DI에 있는 객체 꺼내오기

xml 파일이 잘 읽혔고 Context를 통해 각 객체들이 생성이 되었다면 **IOC 컨테이너**에 담겨져 있을 것입니다.<br>
IOC 컨테이너에서 id나 type명을 통해 꺼내 사용할 수 있습니다.<br>

<br>

- getBean()을 사용하여 "console"을 id로 가지는 객체를 가져옵니다. 이때 객체 타입이 object이기 때문에 형식 변환을 해서 사용해주어야합니다.

      ExamConsole console = (ExamConsole) context.getBean("console");
 
- class를 통해 불러오는 경우는 형 변환이 따로 필요 없습니다.

      ExamConsole console = (ExamConsole) context.getBean(ExamConsole.class);
      
- setting.xml을 다시 봅시다.

    ```
	<bean id="console" class="spring.di.ui.newGridExamConsole">
		<property name="exam" ref="exam" />
	</bean>
    ```
      
   newGridExamConsole/InlineExameConsole을 넣느냐에 따라서 결과값이 달라지는 것을 확인할 수 있습니다.<br>
    
<br>
    

# 참고

- [https://www.youtube.com/watch?v=bYu9MNLBvX0&list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T&index=7](https://www.youtube.com/watch?v=bYu9MNLBvX0&list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T&index=7)
- [https://youtu.be/R_6fW1tVj8Y?list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T](https://youtu.be/R_6fW1tVj8Y?list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T)
