---
title:  "제어의 역전(Inversion of Control) 과 의존성 주입(Dependency Injection)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Spring
tags:
  - IoC
  - Inversion of Control
  - DI
  - Dependency Injection
  - Spring
  - 제어의 역전
  - 의존성 주입
  - 스프링
toc: true
toc_sticky: true
---

기존의 어플리케이션 코드는 제어권을 가지고 능동적으로 라이브러리를 사용하여 어플리케이션을 개발하지만, IoC(Inversion of Control)는
이 제어권이 역전된 것을 의미하며 프레임워크가 제어권을 가지고 어플리케이션 코드를 능동적으로 호출하여 사용한다.

이러한 제어권을 가지고 있는 것이 컨테이너(Container)이다. 컨테이너는 객체의 생성과 생성주기까지 모든 것을 관리한다.

## 사용이유

- 클래스 호출 방식 : 클래스 내에 선언과 구현이 같이 존재하기 때문에 다양한 형태의 변화가 어렵다.

- 인터페이스 호출 방식 : 클래스를 인터페이스와 클래스로 나누어 선언과 구현을 분리, 구현클래스 교체가 용이하고 다양한 변화가 가능하다. 하지만 구현클래스 교체시에 호출클래스의 수정이 필요하다.

- 팩토리 호출 방식 : 팩토리가 구현클래스를 생성하고 호출클래스는 백토리를 호출, 구현클래스 변경시에 팩토리만 수정하면 되므로 호출클래스에는 영향을 미치지 않는다. 하지만 팩토리에 의존한다.

- 위 세가지의 과정을 거쳐 팩토리의 장점을 더한 IoC가 나타났다. 어떠한 것에도 의존하지 않는 형태로 실행시점에 클래스간의 관계가 형성이 되며 의존성이 삽입된다고도 하여 이를 DI(Dependency Injection)라 부른다.

## 주요 용어

- bean : 스프링 컨테이너가 생성하고 관계설정, 사용을 제어해주는 오브젝트를 말한다.
- bean factory : 스프링의 IoC를 담당하는 핵심 컨테이너를 말한다.
- application context : bean factory를 확장한 IoC 컨테이너를 말한다.
- configuration metadata : application context 혹은 bean factory가 IoC를 적용하기 위해 사용하는 메타정보를 말한다.
- container : IoC 방식으로 bean을 관리한다는 의미에서 bean factory나 application context를 가리킨다.


