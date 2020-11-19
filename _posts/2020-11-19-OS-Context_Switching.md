---
title:  "컨텍스트 스위치(Context Switching)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Operating System
tags:
  - 컨텍스트 스위치
  - 운영체제
  - Context Switching
  - Operating System
toc: true
toc_sticky: true
---

Context Switching(Process switching)이란 실행 중인 프로세스의 context를 저장하고, 앞으로 실행 할 프로세스의 context를 복구 하는 일, 위의 saving과 restoring하는 작업을 뜻하며 커널의 개입으로 이루어진다.

## Context
- 프로세스와 관련된 정보들의 집합
	- CPU register context : CPU안에 존재한다.
	- Code & data, Stack, PCB : 메모리 안에 존재한다.

## Context saving
- 현재 프로세스의 Register context를 저장하는 작업

## Context restoring
- Register context를 프로세스로 복구하는 작업

## Context Switch Overhead
- Context switching에 소요되는 비용으로 OS마다 다르며, 성능에 큰 영향을 준다
- 불필요한 Context switching을 줄이는 것이 중요하다.
	- 스레드(thread)사용 등
