---
title:  "페이징 기법(Paging System)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Operating System
tags:
  - 페이징 기법
  - 운영체제
  - Paging System
  - Operating System
toc: true
toc_sticky: true
---

페이징 기법(Paging System)은 프로그램을 고정된 크기의 block으로 분할하고 메모리를 block size로 미리 분할하여 메모리를 관리하는 기법이다.

## 장점
- 필요한 page만 page frame에 적재하여 사용하기 때문에 간단하고 메모리를 효율적으로 사용한다.
- 외부 단편화(external fragmentation)문제가 없다.
- 메모리 통합/압축이 불필요하다.

## 단점
- 내부 단편화(internal fragmentation)문제가 발생할 수 있다.
- 프로그램의 논리적 구조를 고려하지 않았다.
- Page sharing과 protection이 복잡하다.

## 주소 매핑
- 가상 주소 : v = (p, d)
  - p : page number
  - d : displacement(offset)
- PMT(Page Map Table) 사용
- Direct mapping
- Associative mapping
- Hybrid direct/associative mapping

## Direct mapping(직접 사상)

### 과정
1. 해당 프로세스의 PMT가 저장되어 있는 주소 b에 접근한다.
2. 해당 PMT page p에 대한 entry를 찾는다.
3. 찾은 entry에서 존재 비트를 검사한다. 존재 비트가 0인경우, page fault이며 swap device에서 page를 메모리로 적재한 뒤, PMT를 갱신 한 후 1인경우를 수행한다. 1인경우, 해당 entry에서 page frame번호를 확인한다.
4. page frame번호와 가상 주소의 변위 d를 사용하여 실제 주소 r을 형성한다.
5. 실제 주소 r로 주기억장치에 접근한다.

### 단점
- 메모리 접근 횟수가 2배이다.
- PMT를 위한 메모리 공간이 필요하다.

## Associative mapping(간접 사상)
- 전용 하드웨어인 TLB(Translation Look-aside Buffer)에 PMT 적재
- PMT를 병렬 탐색
- Low overhead, high speed

### 단점
- 비용이 비싸기 때문에 큰 PMT를 다루기가 어렵다.

## Hybrid direct/associative mapping
- 위 두 기법을 혼합하여 사용한다.
- 작은 크기의 TLB를 사용한다.
- 메모리(커널 공간)에 PMT를 저장한다.
- PMT중 최근에 사용된 page에 대한 일부 entry를 TLB에 저장한다.
- Locality(지역성)를 활용한다.
- 프로세스의 PMT가 TLB에 적재되어 있는 경우, 존재 비트를 확인하여 page frame번호를 확인한다.
- 프로세스의 PMT가 TLB에 적재되어 있지 않은 경우, Direct mapping으로 page frame번호를 확인하고 해당 PMT entry를 TLB에 적재한다.
