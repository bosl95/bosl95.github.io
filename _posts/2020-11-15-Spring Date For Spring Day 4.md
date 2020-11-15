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

이어서 계속...

# 참고

- [https://www.youtube.com/watch?v=bYu9MNLBvX0&list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T&index=7](https://www.youtube.com/watch?v=bYu9MNLBvX0&list=PLq8wAnVUcTFUHYMzoV2RoFoY2HDTKru3T&index=7)
