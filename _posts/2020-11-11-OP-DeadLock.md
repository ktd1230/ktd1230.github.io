---
title:  "교착상태(DeadLock)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Operating System
tags:
  - 교착상태
  - 운영체제
  - DeadLock
  - Operating System
toc: true
toc_sticky: true
---

`DeadLock`은 프로세스가 자원을 얻지 못해 다음 처리를 하지 못하는 상태로, `교착 상태`라고도 하며 시스템적으로 한정된 자원을 여러 곳에서 사용하려고 할 때 발생한다.


## 교착 상태(DeadLock)의 발생 조건

교착 상태는 한 시스템 내에서 다음의 네 가지 조건이 동시에 성립 할 때 발생한다.

### 1. 상호 배제(Mutual exclusion)

자원은 한 번에 한 프로세스만 사용할 수 있어야 한다.

### 2. 점유 대기(Hold and wait)

최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 있어야 한다.

### 3. 비선점(No preemption)

다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없어야 한다.

### 4. 순환 대기(Circular wait)

프로세스의 집합{P0, P1, ... , Pn}에서 P0는 P1이 점유한 자원을 대기하고 P1은 P2가 점유한 자원을 대기하고, ... , Pn-1은 Pn이 점유한 자원을 대기하며 Pn은 P0가 점유한 자원을 요구해야 한다.

## 교착 상태(DeadLock) 해결 방법

### 예방법(Prevention)

교착 상태 발생 조건 중 하나를 제거함으로써 해결하는 방법

#### 1. 상호 배제(Mutual exclusion) 부정

여러 개의 프로세스가 공유 자원을 사용할 수 있도록 한다.

#### 2. 점유 대기(Hold and wait) 부정

프로세스가 실행되기 전 필요한 모든 자원을 할당한다.

#### 3. 비선점(No preemption) 부정

자원을 점유하고 있는 프로세스가 다른 자원을 요구할 때 점유하고 있는 자원을 반납하고, 요구한 자원을 사용하기 위해 기다리게 한다.

#### 4. 순환 대기(Circular wait) 부정

자원에 고유한 번호를 할당하고, 번호 순서대로 자원을 요구하도록 한다.

### 회피법(Avoidance)

교착 상태(DeadLock)가 발생하면 피해나가는 방법

- 은행원 알고리즘(Banker’s Algorithm)

### 탐지(Detection)



### 회복(Recovery)

