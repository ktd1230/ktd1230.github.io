---
title:  "오버로딩(Overloading)과 오버라이딩(Overriding)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Java
tags:
  - 자바
  - 오버로딩
  - 오버라이딩
  - Java
  - Overloading
  - Overriding
toc: true
toc_sticky: true
---

오버로딩과 오버라이딩은 서로 혼동하기 쉽지만 사실 그 차이는 명백하다. 오버로딩은 기존에 없는 새로운 메서드를 추가하는 것이고, 오버라이딩은 조상으로부터 상속받은 메서드의 내용을 변경하는 것이다.

## 오버로딩(Overloading)

- 한 클래스 내에 같은 이름의 메서드를 여러 개 정의하는 것을 '메서드 오버로딩(method overloading)'또는 간단히 '오버로딩(overloading)'이라 한다.

### 오버로딩의 조건

- 메서드 이름이 같아야 한다.
- 매개변수의 기수 또는 타입이 달라야 한다.
- 반환 타입은 오버로딩을 구현하는데 아무런 영향을 주지 못한다.

### 오버로딩의 장점

- 기억해야 하는 함수의 갯수가 줄어 오류의 가능성을 많이 줄일 수 있다.
- 같은 이름의 함수라면 같은 기능을 할 것이라 쉽게 예측할 수 있다.
- 메서드의 이름을 절약할 수 있다.

## 오버라이딩(Overriding)

- 조상 클래스로부터 상속받은 메서드의 내용을 변경하는 것을 오버라이딩(overriding)이라고 한다. 상속받은 메서드를 그대로 사용하기도 하지만, 자손 클래스 자신에 맞게 변경해야 하는 경우가 많다. 이럴 때 조상의 메서드를 오버라이딩 한다.

### 오버라이딩의 조건

- 이름이 같아야 한다.
- 매개변수가 같아야 한다.
- 반환타입이 같아야 한다.

#### 접근 제어자(access modifier)와 예외(exception)의 변경가능 조건

- 접근 제어자는 조상 클래스의 메서드보다 좁은 범위로 변경 할 수 없다.
- 조상 클래스의 메서드보다 많은 수의 예외를 선언할 수 없다.
- 인스턴스메서드를 static메서드로 또는 그 반대로 변경할 수 없다.