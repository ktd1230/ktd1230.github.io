---
title:  "선형리스트(ArrayList)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Data Structure
tags:
  - 선형리스트
  - 자료구조
  - ArrayList
  - Data Structure
toc: true
toc_sticky: true
---

ArrayList는 논리적 저장 순서와 물리적 저장 순서가 일치하는 기본적인 자료구조이다. 배열을 기반으로 구현되어 있어 인덱스를 이용한 접근이 가능하다.


## 장점

- 무작위 접근(Random Access)이 가능하여 특정 자료의 탐색 속도가 빠르다.
- 기억장소를 연속적으로 배정받기 때문에 기억장소 이용 효율은 밀도가 1로서 가장 좋다.


## 단점

- 삽입 시에 배열의 공간을 늘려야 하고, 만약 기존 데이터 사이에 새로운 데이터의 삽입이 발생한다면 모든 원소를 한 칸씩 움직여야 하기 때문에 불리하다.
- 삭제 시에 삭제된 자리를 채우기 위해 모든 원소들을 한 칸씩 이동해야 하기 때문에 불리하다.