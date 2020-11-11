---
layout: post
title: "Spring Date For Spring Day (2)"
tags: [java, spring, spring boot, 스프링부트]
comments: true
---

Spring boot 두번째<br>

- 이전 글 : [[Spring Date For Spring Day (1)]](https://bosl95.github.io/spring-date-for-spring-day/)

# 서블릿이란 무엇인가?

  > "클라이언트의 요청을 처리하고, 그 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍 기술"
  
  
  자바를 사용하기 위하여 JRE(Java Runtime Enviroment)가 필요한 것처럼, 서블릿을 실행하기 위해서는 웹 서버가 필요하다.<br>
  서블릿은 Java EE(Enterprise Edition)에 포함된 스펙인데, 자바에서 HTTP 요청과 응답을 처리하기 위한 내용을 담고 있다.<br>

- JAVA EE의 스펙 (survlet을 확인할 수 있다.)

    ![image](https://user-images.githubusercontent.com/34594339/98806382-77c62e80-245c-11eb-9abb-ac6d3b4a0b29.png)
    
<br>

### 서블릿의 특징

- 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트
- html을 사용하여 요청에 응답한다.
- Java THread를 이용하여 동작한다.
- MVC 패턴에서 Controller로 이용된다.
- HTTP 프로토콜 서비스를 지원하는 javax.servlet.http.HttpServlet 클래스를 상속받는다.
- UDP보다 처리속도가 느리다.
- HTML 변경 시 Servlet을 재컴파일해야하는 단점이 있다.

<br>



# 참고

- [서블릿이란?](https://mangkyu.tistory.com/14)
