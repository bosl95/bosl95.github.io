---
layout: post
title: "백엔드 개발을 꿈꾸는 학생의 기록"
tags: [백엔드, backend]
comments: true
---

백엔드 개발자를 꿈꾸며, <br>
늦었다는 생각 보다는 지금 당장 내가 무엇을 할 수 있을 지에 대해서 찾아본 정보들을 기록해 보려고 합니다.<br>

# 백엔드 개발자에 대해 알아보자

## 1. 백엔드  개발자는 무슨 일을 하나요?

- 백엔드 개발자는 다른 개발 분야에 비하면 하는 일이 상대적으로 모호합니다.
- 프로젝트에 따라서 서버/DB관리나 프론트엔드 개발까지 모두 담당하기도 합니다.
- 폭넓은 기술을 접할 수 있는 역할을 수행합니다.
- SE(System engineer), FE(Front End) 등 인접한 분야의 개발자와 소통할 기회가 많습니다.
- 접한 분야 중 한 분야에 대한 전문성을 키울 기회를 만나기가 쉽습니다. (예를 들면 시스템 통계 모듈 개발에서 대용량 데이터를 다루는 데이터 엔지니어로 성장하는 경우)


<br>

## 2. 백엔드 개발의 어려운 점과 개발하면서 느낀 매력은 무엇인가요?

- 백엔드 개발은 시스템을 안정적이고 효율적으로 만들 때 보람을 느낍니다.
- 성능을 획기적으로 개선했을때
- 모듈 구조를 개선해 코드를 줄였을 때
- 에러 없이 서버 프로그램이 실행 될 때 등 겉으로 잘 드러나지 않는 영역이기도 합니다.

<br>

## 3. 다양한 도구와 프레임워크가 개발되는 상황에서 백엔드 개발의 비전에 대해서 어떻게 생각하시는 지?

- 해야할 과제가 늘어가는 속도에 비하면 도구 등의 의한 생산성 증가 속도는 느리다고 느껴집니다.
- 새로운 도구/프레임워크는 기존의 문제를 해결하고 개선하기 위해 나온 것입니다. 따라서 기존 기술을 쓰면서 깊이 있는 고민을 한 사람이라면 새로운 도구에 더빨리 적응하고 응요할 수 있을 것입니다.
- 다만 개발 분야에 따라 흥망성쇄가 갈릴 수 있다고 생각합니다.
  - Flash 기반 UI 개발 수요가 많았으나 현재, 이전만큼 Flash 개발자를 찾지 않게 되었습니다.
- 기존 기술을 깊게 이해하신 분들은 새로운 환경에서도 뛰어난 개발자로 정착하는 경우가 많습니다.
  - Flash에서 사용하는 ActionSCript를 잘 쓸 수 있던 개발자들이 웹 FE 개발자로 전화하는 경우가 많습니다.
- 한번 맡은 분야를 끝까지 담당한다는 보장은 없기에 새로운 개발 분야에 적응할 수 있는 역량을 키워두는 것이 좋습니다.
- 백엔드 개발은 여러 분야와 연결되기에 그런 면에서 무난한 선택입니다.

<br>

## 4. 머신러닝/빅데이터 기술의 발달이 백엔드 개발에 미칠 영향이 있을까요?

- 백엔드 개발을 하다가 데이터 분석, 모델링 업무에 참여하는 경우도 늘어날 것 같습니다.
- 이론적인 바탕이 튼튼하더라도 특정 분야에 의미있는 분석/모델링을 하기 위해서는 그 도메인을 이해하는 것이 중요합니다.
- 서비스 개발을 하면서 사용자의 특성을 이해한 개발자가 이론적인 깊이까지 갖춘다면 가치가 더 높아질 것입니다.
- 직접적으로 분석/모델링을 수행하지 않더라도 많은 백엔드 개발자는 이를 뒷받침하는 개발을 하게 될 것입니다.
  - 깊이 있는 데이터 분석을 위해서는 데이터를 단순히 RDB같은 하나의 저장소에 쌓아두는 것만으로는 부족합니다. 
  - 이전에는 그냥 버렸던 로그성 데이터들도 어떻게 활용할 수 있을지 분석하기 좋게 저장을 할지 고민을 더 하게 되었습니다.
  - 담당하는 서비스가 많은 사용자와 데이터를 받을 정도로 운영되어야 머신러닝 같은 고급기법으로 분석할 만큼 많은 데이터가 쌓일 것입니다. 넓게 보면 대용량의 서비스를 개발하는 백엔드 개발자는 AI/빅데이터와 시대의 과제와 맞닿아 있습니다.
 
 <br>

## 5. 백엔드 개발에 필요한 지식이 있을까요?

- 주로 JVM과 Linux를 바탕으로한 환경에서 서버 모듈을 개발하신 분이었습니다.

- 웹 서버를 개발할 때 떠오르는 요소들

  - 웹 생태계 스펙
    - HTML, HTTP(1.1, HTTP/2)
  - 기본 SDK, 라이브러리/프레임워크 이해와 활용
  - 클라이언트를 위한 API 설계
  - 서버/컴포넌트/객체 간의 역할 분담/의존성/통신 방법 설계
  - 저장소 활용
    - DBMS 설계
    - Cache 적용
      - Global/Local cahce 적용 범위, 라이프 싸이클, 솔루션 선택
    - 파일 저장 정책/ 솔루션 선택 활용
  - 검색 엔진 연동 방식 결정
  - 빌드 도구
    - Maven/Gradle
  - 배포 전략
  - 성능 테스트/프로파일링/튜닝
    - JVM 레벨의 튜닝 (GC 옵션 등)
      - 웹 서버 (Nginx, Tomcat) 등의 설정/튜닝
    - OS 설정의 주요 값 확인
  - 인접 기술에 대한 이해
    - DBMS, Front end 등
  - 서버 개발자에만 해당하지 않는 항목
    - 테스트 코드 작성/리팩토링 기법
    - 버전 관리 전략
      - branch 정책 등
      
<br>
      
## 6. 데이터베이스를 어디까지 알아야 할까요?

- 다양한 저장소가 쓰이는 시대에도 RDB(관계형 데이터베이스)는 여전히 가장 우선시되는 저장소입니다.
- 그래서 RDB를 잘 다루는 능력은 백엔드 개발자의 핵심 역량 중 하나입니다.

  > RDB란? <br>
  > 관계형 데이터 모델에 기초를 둔 데이터베이스이다. 관계형 데이터 모델이란 데이터를 구성하는데 필요한 방법 중 하나로 모든 데이터를 2차원의 테이블 형태로 표현해 준다.<br>
  > 관계형 데이터 모델의 개념은 표현 개체의 외부개념 관례를 적용한 것으로, 데이터 간의 상관관계를 개체간의 관계를 표현한 것이라고 할 수 있다.
  
- 개발을 하는 도중에도 쿼리의 호출 횟수나 실행 계획이 비효율적이지 않은지 확인하는 습관이 필요합니다
- 운영 중에도 느린 쿼리를 모니터링하고 DBA와 협업하여 성능 개선을 하는 작업을 실무개발자들은 꾸준히 하고 있습니다.
- ORM같은 추상화된 프레임워크를 써서 직접 SQL을 작성하지 않는 경우에도 그런 작업들은 더욱 중요합니다.
- 과거엔 서버간 네트워크 호출 비용을 줄이기위해 한번에 많은 테이블을 조인하는 긴 SQL을 만들었으나, 요즘은 JOIN을 가급적 피하는 경항이 생겼습니다.
- 데이터를 조회하는 SQL이 단순할 수록 데이터를 다른 저장소에 캐시하거나 분산해서 저장하기가 쉬워집니다.
- 대용량 저장하는 UGC 서비스에서는 RDB 테이블 사이의 JOIN은 최대한 제약을 하고 어플리케이션 레벨에서 여러 저장소의 연관된 데이터를 조합하기도 합니다.

... 이어서 계속... 

<br>







