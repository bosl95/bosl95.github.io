---
layout: post
title: "Computational Thinking"
tags: [CT, computational thinking]
comments: true
---

요즘 대두되고 있는 Computational Thinking에 대해서 알아보자.

# Computational Thinking의 개념

- 단어 그대로 컴퓨터적인 사고 연산을 의미
- 생각하는 것을 구현하기 전에 해야할 일을 바로 생각하는 것을 컴퓨터가 이해할 수 있는 구조로 바꾸는 것

<br>

## 자료구조

### 1. 비트 연산
  
- 컴퓨터의 언어는 0과 1로 구성되어 있다.
- 비트와 바이트
  - Bit(비트) : 0과 1 하나만 표현하는 가장 작은 단위
  - Bytes(바이트) : 비트 8개를 하나로 묶은 단위 (2<sup>8</sup>=256가지의 수 표현 가능)
  - 정수 하나 = 4Byte (2<sup>32</sup>=약 42억 수 표현)

- 2진법 음수 표현법
  - 0에서 원하는 수의 양수를 뺀 것이 해당 수의 음수 표현
  - 양수를 음수로 바꾸는 순서
    1. 비트를 0에서 1로, 1에서 0으로 바꾸어준다.
    2. 바꾼 비트에 1을 더해준다.

<br>

### 2. 스택

- push와 pop을 통해 요소를 넣거나 뺄 수 있으며 후입선출(LIFO, Last In First Out)이다.
- [[자료구조 더 알아보기]](https://davinci-ai.tistory.com/16?category=911813)

<br>

### 3. 큐

- enqueue(또는 push)와 dequeue(또는 pop)을 통해 요소를 넣거나 뺄 수 있으며, 선입선출(First In First Out)입니다.
- [큐에 대해 더 알아보기](https://davinci-ai.tistory.com/16?category=911813)
- "n명의 사람이 원형 테이블로 앉아있을 때, 1번 사람부터 원에서 나가고, 나간사람으로부터 k번째 사람이 차례대로 나가는 문제"

<br>

### 4. 그래프

- 유향 그래프 : 방향이 존재하는 그래프
- 무향 그래프 : 방향이 존재하지않는 그래프
- Cycle : 같은 간선을 두번 이상 지나지 않고 돌아올 수 있는 경우
- 문제 예시

  > 무게가 다른 n개의 구슬이 있을 때 k번의 구슬 두개씩의 크기 대소 비교 측정 결과가 주어진다.<br>
  > 이때, 자신이 몇번째로 무거운 구슬인지 아는 구슬의 수를 구하는 문제<br>
  > 그래프로 각 번호의 구슬을 연결시켜서 해결한다.<br>

<br>

### 5. 트리

<image src='https://user-images.githubusercontent.com/34594339/98506259-6d5e3600-229e-11eb-855a-cadf029351c5.png' width='70%'>

- Node : 트리를 구성하는 각각의 정보(요소)
- Root : 트리에 계층이 존재한다. 가장 높은 곳을 루트라 부른다.
- Edge : 각 노드들의 관계를 간선으로 이은 것
- 노드의 수가 n개 일 때, Edge의 개수는 n-1개이다. 
- 이진트리 : 각 노드가 최대 2개의 자식 노드를 가지는 트리 구조

- 이진트리 순회
  1. 전위 순회 : 현재 노드 > 왼쪽 노드 > 오른쪽 노드 순서로 순회 진행
    
    <image src='https://user-images.githubusercontent.com/34594339/98507201-75b77080-22a0-11eb-9bcf-0d276f6a686a.png' width='70%'>
    
    - 맨 앞의 노드가 루트 노드이다.
    
    <br>
    
  2. 중위 순회 : 왼쪽 노드 > 현재 노드 > 오른쪽 노드 순서로 순회 진행
  
    <image src='https://user-images.githubusercontent.com/34594339/98507207-76e89d80-22a0-11eb-9d03-9f72902a57f7.png' width='70%'>
    
    - 각 노드의 상대적인 위치를 확인할 수 있다. 
    
    <br>
    
  3. 후위 순회 : 왼쪽 노드 > 오른쪽 노드 > 현재 노드 순서로 순회 진행
    
    <image src='https://user-images.githubusercontent.com/34594339/98507207-76e89d80-22a0-11eb-9d03-9f72902a57f7.png' width='70%'>
  
    - 맨 뒤의 노드가 루트 노드이다.<br>

<br>

## 참고 사이트

- [https://davinci-ai.tistory.com/37?category=931528](https://davinci-ai.tistory.com/37?category=931528)
