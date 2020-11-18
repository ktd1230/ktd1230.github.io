---
title:  "웹서버(Web Server)와 WAS(Web Application Server)"
header:
  teaser: "/assets/images/500x300.png"
categories: 
  - Network
tags:
  - WAS
  - Web Application Server
  - Web Server
  - 웹서버
  - 네트워크
toc: true
toc_sticky: true
---

## 웹 서버(Web Server)

웹 서버(Web Server)는 클라이언트로부터 HTTP 요청을 받아 `정적인 웹 서비스`(HTML 문서나 각종 리소스)를 제공하는 컴퓨터를 의미한다.

- Apache, Nginx

## WAS(Web Application Server)

WAS(Web Application Server)는 Web Server + Web Container로 이루어져 있으며 html의 한계를 어플리케이션을 통해서 극복하고 Web Container에서 servlet, php, jsp, asp와 같은 언어들을 사용해 `동적인 페이지`를 생성할 수 있고, 프로그램 실행 환경과 데이터베이스 접속 기능 제공, 비즈니스 로직 수행을 수행하고 그 결과를 웹 서버에게 전달함으로써 동적인 웹 서비스를 제공할 수 있다.

- Tomcat, Jeus, JBoss
