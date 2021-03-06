---
title:  "SSL 동작방법"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Network
tags:
  - SSL
  - https
  - Network
toc: true
toc_sticky: true
---

SSL은 암호화된 데이터를 전송하기 위해서 공개키와 대칭키를 혼합해서 사용한다. 즉 클라이언트와 서버가 주고 받는 실제 정보는 대칭키 방식으로 암호화하고, 대칭키 방식으로 암호화된 실제 정보를 복호화할 때 사용할 대칭키는 공개키 방식으로 암호화해서 클라이언트와 서버가 주고 받는다.

## 1. handshake

1. 클라이언트가 서버에 접속한다. 이 단계를 Client Hello라고 한다.
- 클라이언트 측에서 생성한 랜덤 데이터
- 클라이언트가 지원하는 암호화 방식들 : 서로 협상하기 위해
- 세션 아이디 : 이전 SSL handshaking 했다면 기존의 세션 재활용하기 위해서

2. 서버는 Client Hello에 대한 응답으로 Server Hello를 하게 된다.
- 서버 측에서 생성한 랜덤 데이터
- 서버가 선택한 클라이언트의 암호화 방식
- 인증서

3. 클라이언트는 서버의 인증서가 CA에 의해서 발급된 것인지를 확인하기 위해서 클라이언트에 내장된 CA 리스트를 확인한다.
- CA 리스트에 인증서가 없을 때 : 사용자에게 경고 메시지를 출력한다.
- 클라이언트에 내장된 CA의 공개키를 이용해서 인증서를 복호화한다. 복호화에 성공했다면 인증서는 CA의 개인키롤 암호화된 문서임이 보증되고 서버를 믿을 수 있다.
- 인증서가 복호화 되면 그 안에 서버가 넣어놓은 공개키를 클라이언트는 획득하게 된다.
- 또한, 1, 2번 과정에서 주고받은 랜덤데이터를 이용해서 클라이언트는 pre master secret이라는 대칭키를 생성하고 이는 인증서에서 획득한 공개키로 암호화하여 서버에 전송한다.

4. 서버는 클라이언트로부터 받은 pre master secret값을 자신의 비공개키(비밀키)로 복호화한다.
- 서버와 클라이언트는 공통된 pre master secret값을 안전하게 갖게 되었다.
- 서버와 클라이언트는 pre master secret -> master secret -> session key를 생성하게 된다.
- session key를 이용하여 둘은 대칭키 암호화 방식으로 세션단계에서 데이터를 주고받게 된다.

5. handshake 종료를 서로에게 알린다.

## 2. 세션

서버와 클라이언트는 실제 데이터(아이디나 비밀번호)들을 session key로 대칭키 방식으로 암호화 하여 주고받는다.

## 3. 세션 종료

데이터의 전송이 끝나면 SSL 통신이 끝났음을 서로에게 알려준다. 이 때 사용했던 대칭키인 session key를 폐기한다.