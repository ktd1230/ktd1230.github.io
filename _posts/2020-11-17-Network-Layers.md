---
title:  "네트워크 계층(OSI 7 Layers)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Network
tags:
  - OSI 7 Layers
  - Network
  - 네트워크 계층
  - 네트워크
toc: true
toc_sticky: true
---

네트워크 계층 OSI(Open System Interconnection) 7 Layers은 통신이 일어나는 과정을 7단계로 나눈 것을 의미한다.

## 1. 물리 계층(Pysical Layer)

- 데이터를 전송하기 위해 아날로그신호로 인코딩하고 받아서 디지털신호로 디코딩하는 작업을 하는 모듈이다.
- Data Unit : Bit
- 장비 : 케이블, 리피터, 허브

### 물리 계층 프로토콜

- RS-232 : 보통 15m이하 단거리에서 38400bps까지 전송을 위한 직렬 인터페이스
- X.25 : 패킷교환망에 대한 액세스 표준
- X.21 : 회선교환망에 대한 액세스 표준

## 2. 데이터링크 계층(Data Link Layer)

- 물리 계층을 통해 송수신되는 정보의 오류와 흐름을 관리하여 안전한 정보의 전달을 수행할 수 있도록 도와주는 역할을 한다.
- 두 지점 간의 신뢰성 있는 전송을 보장한다.
- 맥주소(MAC Adress)를 부여한다.
- Data Unit : Frame / Bit
- 장비 : 브리지, 스위치

### 데이터링크 계층 프로토콜

- Ethernet : 비연결성(connectionless)모드, 전송속도 10Mbps 이상, LAN 구현 방식
- HDLC(High-Level Data-Link Control) : 고속 데이터 전송에 적합하고, 비트 전송을 기본으로 하는 범용의 데이터 링크 전송제어절차
- PPP(Point-to-Point Protocol) : 전화선 같이 양단간 비동기 직렬 링크를 사용하는 두 컴퓨터간의 통신을 지원하는 프로토콜

## 3. 네트워크 계층(Network Layer)

- 데이터를 목적지까지 가장 안전하고 빠르게 전달하는 기능을 하는 모듈이다.
- IP주소와 같이 어디로 가야할지 주소정보를 추가한다.
- 경로를 설정한다.
- Data Unit : Packet / Datagram
- 장비 : 라우터, L3 스위치

### 네트워크 계층 프로토콜

- IP(Internet Protocol)
  - 패킷 교환 네트워크에서 정보를 주고받는데 사용하는 정보 위주의 규약
  - 호스트의 주소지정과 패킷 분할 및 조립 기능을 담당
- ICMP(Internet Control Message Protocol)
  - TCP/IP에서 IP 패킷을 처리할 때 발생되는 문제(오류 보고)를 알림
  - 진단 등과 같이 IP계층에서 필요한 기타 기능들을 수행하기 위해 사용되는 프로토콜
- IGMP(Internet Group Management Protocol)
  - IP 멀티캐스트를 실현하기 위한 통신 프로토콜
  - PC가 멀티캐스트로 통신할 수 있다는 것을 라우터에 통지하는 규약

## 4. 전송 계층(Transport Layer)

- 포트번호와 같이 어떤 프로세스에 관련된 정보인지 추가하는 기능을 하는 모듈이다.
- Data Unit : Segments
- 장비 : L4 스위치

### 전송 계층 프로토콜

- TCP(Transmission Control Protocol)
  - 전송 제어 프로토콜, 네트워크의 정보전달을 통제하는 프로토콜
  - 데이터의 전달을 보증하고 보낸 순서대로 받게 해줌
  - 3 Way HandShaking과 4 Way HandShaking 등을 활용한 신뢰성 있는 전송 기능
- UDP(User Datagram Protocol)
  - 비연결성이고 신뢰성이 없으며, 순서화되지 않은 Datagram 서비스 제공
  - UDP는 신뢰성이 낮은 프로그램에 적합

## 5. 세션 계층(Session Layer)

- 데이터가 통신하기 위한 논리적인 연결을 말한다.
- 통신자 간의 동기화 정보를 추가하는 기능을 하는 모듈이다.
- 동시 송수신 방식(duplex), 반이중 방식(half-duplex), 전이중 방식(full duplex)의 통신방식을 설정한다.
- 통신을 하기 위한 세션을 확립/유지/중단 (운영체제가 한다.)
- Data Unit : Data

### 세션 계층 프로토콜

- NetBIOS : 네트워크의 기본적인 입출력을 정의한 규약
- RPC(Remote Procedure Call) : Windows 운영 체제에서 사용하는 원격프로시저 호출 프로토콜
- WinSock(Windows Socket) : 유닉스 등에서 TCP/IP 통신시 사용하는 Socket을 Windows에서 그대로 구현한 것

## 6. 표현 계층(Presentation Layer)

- 암호화나 데이터 표현(파일의 확장자)의 차이 정보를 추가하는 기능을 하는 모듈이다.
- 문서 파일의 인코딩을 담당하기도 한다.
- Data Unit : Data

### 표현 계층 프로토콜

- SSL(Secure Socket Layer)
  - 네트워크 레이어의 암호화 방식, HTTP 뿐만 아니라, NNTP, FTP 등에도 사용
  - 인증, 암호화, 무결성을 보장하는 프로토콜
- ASCII(American Standard Code for Information Interchange)
  - 문자를 사용하는 많은 장치에서 사용되며, 대부분의 문자 인코딩이 아스키에 기반
  - 7비트 인코딩, 33개의 출력 불가능한 제어 문자들과 공백을 비롯한 95개의 출력 가능한 문자

## 7. 응용 계층(Application Layer)

- 프로그램과 관련된 정보를 추가하는 기능을 하는 모듈이다.
- 일반적인 응용 서비스를 수행한다.
- Data Unit : Data
- 장비 : L7 스위치

### 응용 계층 프로토콜

- HTTP(HyperText Transfer Protocol)
  - WWW(World Wide Web) 상에서 정보를 주고 받을 수 있는 프로토콜
  - 주로 HTMP문서를 주고받는 데에 쓰이고, TCP와 UDP를 사용하며, 80번 포트사용
- SMTP(Simple Mail Transfer Protocol) : 인터넷에서 이메일을 주고받기 위해 이용되는 프로토콜, TCP 포트번호 25번 사용
- FTP(File Transfer Protocol) : 컴퓨터 간 파일을 전송하는 데 사용되는 프로토콜 (데이터 전달 : 20번 포트, 제어정보전달 : 21번 포트)
- TELNET
  - 인터넷이나 로컬 영역 네트워크 연결에 쓰이는 네트워크 프로토콜, IETF STD 8로 표준화
  - 보안문제로 사용이 감소하고 있으며, 원격제어를 위해 SSH로 대체