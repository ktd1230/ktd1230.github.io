---
title:  "인터페이스(Interface)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Java
tags:
  - 인터페이스
  - 자바
  - Interface
  - Java
toc: true
toc_sticky: true
---

인터페이스는 Implements(구현)로 선언한 것을 모두 구현해야 하기 때문에 구현 객체가 같은 동작을 함을 보장 할 수 있다.

## 특징

- 여러 인터페이스를 상속받는 것이 가능하다.

## 용도

- 코드 안에서 협업자 상호간에 구체적인 약속을 하기위해 사용된다.

## 문법

```java
public interface 인터페이스명 {
  // 구현되지 않은 메서드
}
```