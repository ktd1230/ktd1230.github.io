---
title:  "관점 지향 프로그래밍(AOP-Aspect Oriented Programming)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Spring
tags:
  - AOP
  - Aspect Oriented Programming
  - Spring
  - 관점 지향 프로그래밍
  - 스프링
toc: true
toc_sticky: true
---

AOP(Aspect Oriented Programming)은 관점 지향 프로그래밍으로도 불리며 부가기능(인프라 로직)의 관점, 비즈니스 로직의 관점 등과 같이 관점의 기준에서 프로그래밍을 하는 것을 뜻한다.

## 사용이유

- 시간을 재는 것, 권한을 체크 하는 것, 트랜젝션을 거는 것과 같은 인프라로직은 메인 기능 구현부분인 비즈니스 로직이 아니기 때문에 어플리케이션 전 영역에서 나타날 수 있으며 중복 코드가 발생하기 쉽다.

- 이는 유지보수가 힘들고, 비즈니스 로직과 함께 있으면 비즈니스 로직을 이해하기 어려워진다.

## 주요 용어

- Target : 클래스나 메서드 등과 같이 Aspect를 적용하는 곳을 뜻한다.
- Advice : 부가기능의 동작 시점을 결정하는 부분이다.
  - Before : 메소드 실행 전에 동작한다.
  - After : 메소드 실행 후에 동작한다.
  - After-returning : 메소드가 정상적으로 실행된 후에 동작한다.
  - After-throwing : 예외가 발생된 후에 동작한다.
  - Around : 메소드 호출 이전, 이후, 예외발생 등 모든 시점에서 동작한다.
- JoinPoint : 클라이언트가 호출하는 모든 비즈니스 로직(Spring에서는 메소드)부분으로, PointCut의 후보들이다.
- PointCut : JoinPoint 중, 선택된 비즈니스 로직 부분으로 실제 실행되는 기준 부분이다.


