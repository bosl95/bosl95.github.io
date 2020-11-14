---
layout: post
title: "Spring Date For Spring Day (3)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot 세번째<br>
<br>

- 이전 글 : [Spring Date For Spring Day (2)](https://bosl95.github.io/Spring-Date-For-Spring-Day-2/)

# Spring 실습해보기

이전 글에서 설명했던 DI(Dependency Injection)을 직접 작성해보려고 합니다!!! (드디어!!!)<br>

<br>

## 1. Exam interface

우선, 이클립스에 새 프로젝트를 하나 만들고, main 함수에 작성해줍시다.<br>


- 원하는 클래스와 인터페이스 작성하기

  ![image](https://user-images.githubusercontent.com/34594339/99088436-64a79000-260f-11eb-8f20-386f2e6ff4bb.png)


<br>

- Exam 인터페이스 생성하기

  그리고 Exam이라는 인터페이스를 하나 생성해줍니다. 생성할 때 패키지명에 .entity를 붙여 다른 패키지로 생성해줍니다.<br>
  생성된 Exam 인터페이스 안에 `total()` 함수와 `avg()` 함수를 정의해줍시다.<br>

    ![image](https://user-images.githubusercontent.com/34594339/99088577-94ef2e80-260f-11eb-88d3-e99efb5a99a6.png) 
    ![image](https://user-images.githubusercontent.com/34594339/99088679-afc1a300-260f-11eb-8782-385ac6157380.png)

    ![image](https://user-images.githubusercontent.com/34594339/99088984-1777ee00-2610-11eb-927d-e1be1df12e15.png)

<br>

- NewExam 클래스 생성하기 

  아까 빨간줄이 뜨던 NewExam도 entity 패키지 안에 class를 자동 생성해주면<br>

    ![image](https://user-images.githubusercontent.com/34594339/99089180-527a2180-2610-11eb-9b78-dafcb37ffdd6.png)

  이렇게 생성이 완료됩니다!<br>

> 생성된 순서를 보시면 내가 원하는 클래스와 인터페이스 작성 > 인터페이스 작성 > 클래스 작성 순으로 되시는 것을 확인할 수 있습니다. (이것을 TopDown 방식이라고 합니다.)<br>

<br>

- NewExam 구현하기 

  NewExam 내부를 각 함수들의 역할에 맞게 구현하는 과정에서 avg() 함수의 반환값이 float으로 변경되어야 했습니다.<br>

   ![image](https://user-images.githubusercontent.com/34594339/99089770-10051480-2611-11eb-87dc-48e06a6d108b.png)

  이때, 인터페이스인 Exam에도 반환값이 float으로 바뀌어야함에 주의합시다!<br>

<br>

- ExamConsole interface 생성하기 

  마찬가지로 요번에도 ExamConsole 인터페이스와 InlineExamConsol 클래스를 만들어봅시다. 이번엔 ui 패키지에 넣도록 합니다.<br>
  아래 사진을 보시면 제가 이미 생성한 ExamConsole의 인터페이스를 InlineExamConsole 클래스 생성과정에서 자바가 자동 상속해주었습니다.<br>

  ![image](https://user-images.githubusercontent.com/34594339/99089998-61150880-2611-11eb-94b1-142435c0f815.png)

<br>

> ### 생성자를 자동 완성하고 싶을 때 Ctrl+Shift 키를 이용하여 만들 수 있습니다! 만약 내가 원하는 변수를 넣은 생성자를 만들고 싶다면 위의 사진처럼 생성할 수 있습니다. 

<br>

- InlineExamConsole 구현
  InlineExamlConsole 내부 코드를 구현하였습니다! 이때 Exam 인터페이스를 import해야하는 데 단축키는 `Ctrl+Shift+O` 입니다<br>

  ![image](https://user-images.githubusercontent.com/34594339/99091195-e51bc000-2612-11eb-8592-12ebee8d6073.png)
 
<br>

- 실행 결과

      total is 0, avg is 0.000000

<br>

- GridExamConsole 생성하기
  이렇게 다른 클래스를 만들어서 ExamConsole 변수에 넣어 사용할 수 있습니다. <br>

  ![image](https://user-images.githubusercontent.com/34594339/99092016-f9ac8800-2613-11eb-912f-698d07da2a91.png)

<br>


ExamConsole로 선언된 변수가 InlineExamConsole 혹은 GridExamConsole을 조립하면서 바꿔서 사용할 수 있는 것을 확인할 수 있었습니다.<br>
이런 방식을 DI(Dependecy Injection)이라고 합니다!<br>
소스코드를 직접 짜보니 훨씬 이해가 쉽네요!!<br>

<br>
<br>

# Spring DI를 위한 이클립스 플러그인 설치하기

DI를 작업할 때 플러그인을 설치해서 좀 더 사용하기 쉽게 할 수 있습니다!<br>
그럼 플러그인 설치 과정을 봅시다!<br>

<br>

1. 이클립스 마켓 플레이스를 들어가주세요

    ![image](https://user-images.githubusercontent.com/34594339/99152388-cbe34400-26e4-11eb-928c-8f5c7200f1c1.png)

2.  Spring Tools를 설치해줍시다!

    ![image](https://user-images.githubusercontent.com/34594339/99152468-56c43e80-26e5-11eb-8a94-794196082feb.png)

3. 자 이제 spring.di 패키지에서 New > others를 클릭해 밑의 보이는 spring bean 파일을 생성해줍시다. (setting.xml이란 이름으로 생성해주었습니다.)

    ![image](https://user-images.githubusercontent.com/34594339/99152562-dd791b80-26e5-11eb-853a-44d2d126d667.png)
    
4. 설정 파일 확인

       <?xml version="1.0" encoding="UTF-8"?>
       <beans xmlns="http://www.springframework.org/schema/beans"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">


       </beans>

<br>

## 참고

- [https://www.youtube.com/watch?v=gtqctgfywn4&list=RDCMUC5-ixpj8DioZqmrasj6Ihpw&index=5](https://www.youtube.com/watch?v=gtqctgfywn4&list=RDCMUC5-ixpj8DioZqmrasj6Ihpw&index=5)
