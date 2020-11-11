---
layout: post
title: "Spring Date For Spring Day (2)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot 두번째<br>

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

대뜸 MVC 패턴에 대해서 알아본 이유는 이 구조를 보시면 알 수 있습니다.<br>

- ### Spring Framework의 구조

    ![image](https://user-images.githubusercontent.com/34594339/98836965-b6241380-2485-11eb-8960-86ceaf9fedd6.png)

<br>

보시면 MVC, DI, Transaction, AOP 등 연결된 것들에 대해서 차근차근 공부할 계획입니다. <br>
그 중 제일 기초인 MVC 패턴의 기본적인 내용에 대해서 찾아보았습니다.<br>

<br>

# DI (Dependency Injection)

<br>

### (수정 중...)



- 이전 글 : [[Spring Date For Spring Day (1)]](https://bosl95.github.io/spring-date-for-spring-day/)

# 참고


- [MVC 패턴이란?](https://medium.com/@jang.wangsu/%EB%94%94%EC%9E%90%EC%9D%B8%ED%8C%A8%ED%84%B4-mvc-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80-1d74fac6e256)


