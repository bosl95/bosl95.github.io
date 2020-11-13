---
layout: post
title: "Spring Date For Spring Day (2)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot 두번째<br>
<br>

- 이전 글 : [Spring Date For Spring Day (1)](https://bosl95.github.io/spring-date-for-spring-day/)

# MVC란 무엇인가?

MVC란 모델-뷰-컨트롤러(Model-View-Controller)로 소프트웨어 공학에서 사용되는 sw 디자인 패턴이다.<br>
Spring MVC는 MVC 패턴 기반의 웹 프레임 워크를 의미한다.

1. Model : '데이터' 디자인 담당 (ex. 상품 목록, 주문 내역 등)
2. View : '실제로 렌더링되어 보이는 페이지'를 담당 (ex. .jsp 파일들)
3. Controller : '사용자의 요청을 받고 응답을 주는 로직' 담당 (ex. GET 등의 uri mapping)

- Web 서버에 특화되어 만들어진 모듈이라, 개발자가 해야할 영역을 더 적게 만들어 준다.
- 기존 Spring 보다 더 깔끔하고 간편하게 개발 가능하다.

<br>

- ### MVC Model 2 아키텍처
  
    ![image](https://user-images.githubusercontent.com/34594339/98835530-e2d72b80-2483-11eb-9cb1-5bdb5b3aed50.png)

<br>

![image](https://user-images.githubusercontent.com/34594339/98836809-78bf8600-2485-11eb-80d2-78cef623dcf8.png)

> #### "앞선 내용에서 말했던 스트럿츠2가 사용한다는 MVC Model2가 이거였군..!"

<br>

- ### Spring Framework의 구조

    ![image](https://user-images.githubusercontent.com/34594339/98836965-b6241380-2485-11eb-8960-86ceaf9fedd6.png)

<br>
<br>

# DI (Dependency Injection)

### DI란?

- 직접 new 해서 객체를 생성하지 않고, Spring의 DI 컨테이너가 관리하는 의존성 주입을 의미한다.

<br>

### DI 컨테이너란?

- Spring이 관리하는 객체를 스프링 빈(=자바 객체)이라고 하는데 이를 담아놓고 관리하는 상자가 **DI 컨테이너**이다.
- 객체를 외부에서 생성하고, 그 객체를 주입시켜 setter 혹은 생성자를 통해 사용한다는 의미이다.
- 컨테이너가 관리하기 때문에 개발자는 객체 생성에 신경 쓸 필요가 없다.
- 스프링에서는 ApllicationContext를 스프링 컨테이너라고 한다.

<br>

이해는 했지만 글보다 그림으로 보면 더 오래 기억할 수 있을 거 같아 찾아보았습니다.<br>

  ![image](https://user-images.githubusercontent.com/34594339/98946037-b29c9500-2536-11eb-9d13-1c2e12bf287e.png)

<br>

실제 코드로 한번 볼까요?<br>

- 일체형

      class A
      {
        private B b;

        public A(){ 
          b = new B();    // 안에서 생성
        }
      }


- 조립형


      class A
      {
        private B b;        // new를 통해 생성하지는 않습니다.

        public void setB(B b){      // 외부에서 생성된 B의 값을 setter를 통해 주입해줍니다.
          this.b = b;
        }
      }


조립형은 A라는 부품에 B라는 부품을 따로 만들어 setB(B)를 통해 조립해준다는 방식으로 생각하시면 됩니다.<br>
그리고 주입에는 두가지 방법이 있다고 합니다.<br>

1. Setter Injection : 위의 조립형 예시로 들은 setB()함수와 같이 set함수를 통해 B를 A에 조립하는 경우를 의미합니다.
2. Contruction Injection : A의 생성자의 매개변수에 B를 넣어서 조립하는 경우를 의미합니다.

<br>
<br>

# IOC (Inversion Of Control)

제어의 역전이란 의미로, 클라이언트가 객체를 제어하지 않고 외부에서 제어하여 객체를 관리하는 것을 의미합니다.<br>
어떤 객체가 사용할 객체를 직접 선언하여 사용하는 것이 아닌 방법을 통하여(setter, 생성자 등) 주입 받아 사용하는 방식을 뜻합니다.<br>

<br>

## Spring IOC 컨테이너

- IOC 기능을 제공하는 컨테이너로 Bean들을 담고 있다.
- Bean의 정의를 읽어들이고 구성 및 제공하는 역할을 한다.

<br>

### 1. BeanFactory<br>

Bean의 생성과 설정 및 관리를 맡고 있다.<br>

### 2. ApplicationContext<br>

BeanFactory를 상속받고 있기 때문에, BeanFacotry와 같은 일을 한다고 볼 수 있다.<br>

### 3. Bean<br>

컨테이너 안에 들어있는 객체들로, 사용하려면 컨테이너에서 가져와야한다.<br>
여러 annotation을 사용하여 일반적인 객체를 bean으로 등록할 수 있다. 또한 Bean에 등록되어 있는 객체들을 쉽게 주입받아 사용할 수 있다.<br>
의존성 주입은 bean끼리만 가능하다고 한다.<br>

<br>

### Bean의 scope<br>

1. 싱글톤 : 하나만 만들어서 사용
2. 프로토타입 : 매번 다른 객체를 사용

<br>

객체를 Bean으로 등록할 때, 아무 annotation을 붙이지 않으면 Bean들이 싱글톤 scope로 등록된다.<br>
미리 컨테이너 안에 만들어둔 하나의 객체를 사용하기 때문에 메모리나 성능 최적화에 유리하다고 한다.<br>

<br>


# 참고

- [MVC 패턴이란?](https://medium.com/@jang.wangsu/%EB%94%94%EC%9E%90%EC%9D%B8%ED%8C%A8%ED%84%B4-mvc-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80-1d74fac6e256)
- [Spring의 DI란?](https://velog.io/@monkeydugi/Spring-DI%EC%9D%98-%EB%8B%A4%ED%98%95%EC%84%B1)
- [스프링 빈이란?](https://endorphin0710.tistory.com/93)
