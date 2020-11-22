---
title:  "프로세스 동기화(Process Synchronization)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Operating System
tags:
  - 프로세스 동기화
  - 운영체제
  - Process Synchronization
  - Operating System
toc: true
toc_sticky: true
---

프로세스 동기화(Process Synchronization)는 다중 프로그래밍 시스템에서 존재하는 여러 프로세스들이 공유하는 자원 또는 데이터가 있을 때 발생하는 문제를 해결하기 위해서 프로세스 들이 서로 정보를 공유하여 동작을 맞추는 것을 의미한다.

## 관련 용어들
- Shared data(공유 데이터) 또는 Critical data : 여러 프로세스들이 공유하는 데이터
- Critical section(임계 영역) : 공유 데이터를 접근하는 코드 영역(code segment)
- Mutual exclusion(상호 배제) : 둘 이상의 프로세스가 동시에 Critical section에 진입하는 것을 막는 것
- Race condition : 실행 순서에 따라서 결과가 달라지는 것

## Mutual exclusion(상호 배제)

### 소프트웨어적 해결 방법
- Dekker's 알고리즘
- Dijkstra's 알고리즘

#### 단점
- 속도가 느리다.
- 구현이 복잡하다.
- 한 줄의 명령어라도 여러 줄의 기계어로 되어 있을 수 있으므로 선점(preemption)될 가능성이 있다.
- Busy waiting이 발생한다.

### 하드웨어적 해결 방법
- TestAndSet(TAS) 명령어

#### 장점
- 구현이 간단하다.

#### 단점
- Busy waiting이 발생한다.

### OS 기반의 소프트웨어적 해결 방법

#### 1. Spinlock

##### 단점
- 멀티 프로세서 시스템에서만 사용이 가능하다.
- Busy waiting이 발생한다.

#### 2. Semaphore

##### 장점
- 기다리는 프로세스는 block(asleep) 상태가 되므로 Busy waiting이 발생하지 않는다.

##### 단점
- Semaphore queue에 대한 wake-up 순서는 비결정적이기 때문에 Starvation problem이 발생할 수 있다.

#### 3. Eventcount/sequencer

##### 장점
- 기다리는 프로세스는 block(asleep) 상태가 되므로 Busy waiting이 발생하지 않는다.
- FIFO 스케줄링 Queue에 의해 Starvation problem이 발생하지 않는다.
- Semaphore보다 더 low-level control이 가능하다.

### 언어단계의 해결 방법
#### Monitor

##### 장점
- 사용이 쉽다.
- Deadlock등 error 발생 가능성이 낮다.

##### 단점
- 지원하는 언어에서만 사용이 가능하다.
- Critical section접근을 위한 코드생성을 위해 컴파일러가 OS를 이해하고 있어야 한다.