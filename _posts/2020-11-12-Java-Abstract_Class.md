---
title:  "추상클래스(Abstract Class)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Java
tags:
  - 추상클래스
  - 자바
  - Abstract Class
  - Java
toc: true
toc_sticky: true
---

추상클래스는 Extends(확장)으로 클래스들의 공통 기능을 추상화하여 중복을 제거하여 만든 클래스이다. 추상클래스는 객체를 생성할 수 없으며, 실체클래스와 상속관계에 있다.

## 용도

- 공통된 필드와 메서드를 통일할 목적으로 사용한다.
- 실체클래스 구현시, 시간을 절약하기 위해 사용한다.
- 규격에 맞는 실체클래스를 구현하기 위해 사용한다.

## 문법

```java
public abstract class 클래스명 {
  // 필드
  // 생성자
  // 메서드
  // 추상메서드
}
```