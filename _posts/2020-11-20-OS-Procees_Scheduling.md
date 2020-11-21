---
title:  "프로세스 스케쥴링 알고리즘(Process Scheduling Algorithm)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Operating System
tags:
  - 프로세스 스케쥴링 알고리즘
  - 프로세스 스케쥴링
  - 운영체제
  - Process Scheduling Algorithm
  - Process Scheduling
  - Operating System
toc: true
toc_sticky: true
---

프로세스 스케줄링(Process Scheduling)은 여러개의 프로세스가 시스템 내에 존재하고, 이 중 자원을 할당 할 프로세스를 선택하는 것을 프로세스 스케줄링이라 한다. 아래는 기본적인 스케줄링 알고리즘들이다.

## 1. FCFS(First Come First Service)
- Non-preemptive scheduling
- `도착 시간(ready queue기준)`을 기준으로 먼저 도착한 프로세스를 먼저 처리
- 자원을 효율적으로 사용 가능하다
- Batch system에 적합, interative system에 부적합하다.
- 단점
  - Convoy effect : 하나의 수행시간이 긴 프로세스에 의해 다른 프로세스들이 긴 대기시간을 갖게 되는 현상
  - 긴 평균 응답시간

## 2. RR(Round Robin)
- Preemptive Scheduling
- `도착 시간(ready queue기준)`을 기준으로 먼저 도착한 프로세스를 먼저 처리
- `자원 사용 제한 시간(time quantum)`이 있다.
  - System parameter
  - 프로세스는 할당된 시간이 지나면 자원 반납
  - 특정 프로세스의 자원 독점(monopoly) 방지
  - Context switch overhead가 큼
  - 성능을 결정하는 핵심 요소이다.
    - 매우 크다면, FCFS
    - 매우 작다면, processor sharing -> Context switch overhead가 매우 커진다.
- interative system(대화형), 시분할 시스템에 적합하다.

## 3. SPN(Shortest Process Next)
- Non-preemptive scheduling
- `실행시간(burst time)`을 기준으로 실행시간이 가장 작은 프로세스를 먼저 처리한다.

### 장점
- 평균 대기시간 최소화
- 시스템 내 프로세스 수 최소화 : 스케줄링 부하 감소, 메모리 절약 -> 시스템 효율 향상
- 많은 프로세스들에게 빠른 응답 시간 제공

### 단점
- Starvation(무한대기) 현상 : Burst Time(실행시간)이 긴 프로세스는 영원히 자원을 할당 받지 못할 수 있다. - > Aging등으로 해결
- 정확한 실행시간을 알 수 없다. -> 예측기법이 필요

## 4. SRTN(Shortest Remaining Time Next)
- SPN의 변형
- Preemptive Scheduling : `잔여 실행 시간`이 더 적은 프로세스가 ready 상태가 되면 선점된다.

### 장점
- SPN의 장점 극대화

### 단점
- 프로세스 생성시, 총 실행 시간 예측이 필요하다.
- 잔여 실행을 계속 추적해야 하고 이로인한 overhead가 발생한다.
- Context Switching overhead
- 구현 및 사용이 비현실적이다.

## 5. HRRN(High Response Ratio Next)
- SPN의 변형
- Non-preemptive scheduling
- Aging concepts : 프로세스의 대기 시간(WT)을 고려하여 기회를 제공
- `Response ratio`가 높은 프로세스를 우선 처리한다.
- Response ratio(응답률) = (WT + BT) / BT
- SPN의 장점을 가지며 Starvation을 방지한다.
- 실행 시간 예측 기법이 필요하다.


## 6. MLQ(Multi level Queue)
- 작업 또는 우선순위별로 `별도의 ready queue`를 가진다.
- 최초 배정된 queue를 벗어나지 못하며, 각각의 queue는 자신만의 스케줄링 기법을 사용한다.
- Queue 사이에는 우선순위 기반의 스케줄링이 사용된다.

### 장점
- 우선순위가 높은 프로세스는 빠른 응답시간을 가진다.

### 단점
- 여러 개의 Queue관리 등 스케줄링 overhead
- 우선순위가 낮은 queue는 starvation현상 발생 가능

## 7. MFQ(Multi level Feedback Queue)
- 프로세스의 `Queue간 이동이 혀용된 MLQ`
- Feedback을 통해 우선 순위를 조정한다.
- 프로세스에 대한 사전 정보 없이 SPN, SRTN, HRRN기법의 효과를 볼 수 있다.

### 특징
- Dynamic priority
- Preemptive scheduling
- Favor short burst-time processes
- Favor I/O bounded processes
- Improve adaptability

### 단점
- 설계 및 구현이 복잡하다.
- 스케줄링 overhead가 크다.
- Starvation문제가 있다.

### 변형
- 각 ready queue마다 시간 할당량을 다르게 배정한다.
- 입출력 위주 프로세스들을 상위 단계의 큐로 이동, 우선순위를 높인다.
- 대기 시간이 지정된 시간을 초과한 프로세스들을 상위 큐로 이동시킨다.