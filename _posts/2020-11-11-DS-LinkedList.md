---
title:  "연결리스트(LinkedList)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Data Structure
tags:
  - 연결리스트
  - 자료구조
  - LinkedList
  - Data Structure
toc: true
toc_sticky: true
---

LinkedList는 논리적 저장 순서와 물리적 저장 순서가 일치하지 않는 기본적인 자료구조이다. 각각의 노드들은 자신의 다음 노드를 기억하고 있다.


## 장점

- 자료의 삽입과 삭제가 유리하다.
- 리스트 내에서 자료의 이동이 필요하지 않다.
- 사용 후 기억 장소의 재사용이 가능하다.
- 연속적인 기억 장소의 할당이 필요하지 않다.

## 단점

- 무작위 접근(Random Access)이 아닌 순차 접근(Sequential Access)으로 인해 특정 자료의 탐색 시간이 많이 소요된다.
- 포인터의 사용으로 인해 저장 공간의 낭비가 있다.
- 알고리즘이 복잡하다.