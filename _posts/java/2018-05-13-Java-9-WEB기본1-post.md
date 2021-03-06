---
layout: post
title: WEB 기본 1
categories: [java]
---

**== WEB기본 정리 1==**<br>

HTTP와 Socket의 가장 큰 차이점은 접속(Connection)을 유지하는지의 여부

물론 파일 전송만을 전문으로 처리하는 FTP통신도 있다.

​     

∘Http 통신

HTTP 는 브라우저가 웹 서버와 통신하기 위해 사용하는 주요 프로토콜이다. 

HTTP Method는 다음과 같다.

⦁GET : 리소스 취득

\- 클라이언트에서 서버로 데이터를 전달할 때, 주소 뒤에 "이름"과 "값"이 결합된 스트링 형태로 전달

\- 주소창에 쿼리 스트링이 그대로 보여지기 때문에 보안성이 떨어진다.

\- 길이에 제한이 있다.(=전송 데이터의 한계가 있다.)

\- Post방식보다 상대적으로 전송 속도가 빠르다.

​     

⦁HEAD  메세지 헤더(문서 정보) 취득

\- GET과 비슷하나, 실제 문서를 요청하는 것이 아니라, 문서 정보를 요청

\- 이에따라 응답 메세지에 본문(Body)이 없이 헤더 만을 보냄

​     

⦁POST : 내용 전송 (파일 전송 가능)

  \- 일정 크기 이상의 데이터를 보내야 할 때 사용한다.

  \- 서버로 보내기 전에 인코딩하고, 전송 후 서버에서는 다시 디코딩 작업을 한다.

  \- 주소창에 전송하는 데이터의 정보가 노출되지 않아 Get방식에 비해 보안성이 높다.

  \- 속도가 Get방식보다 느리다.

  \- 쿼리스트링(문자열) 데이터 뿐만 아니라, 라디오 버튼, 텍스트 박스 같은 객체들의 값도 전송가능.

​     

⦁PUT : 내용 갱신 위주 (파일 전송 가능)

\- POST 처럼 정보를 서버로 제출하는 것으로 형식은 동일하나, 갱신 위주 임

​     

⦁DELETE : 파일 삭제

\- 웹 리소스를 제거 

​     

⦁OPTIONS : 웹서버측 제공 메소드에 대한 질의

\- 가능한 메소드 옵션에 대한 질의

\- 이 경우 응답메세지에 HTTP 헤더 항목 중 `Allow: GET,POST,HEAD` 처럼 보내게 됨

​     

⦁TRACE : (거의 사용 안함)

\- 요청한 메시지의 루프백(loopvack) 테스트를 요청함. 

\- 서버로부터 받은 내용을 클라이언트 쪽에서 확인하기 위해 사용.

\- 테스트 목적 또는 문제 해결을 위해 사용함

​     

⦁CONNECT : (거의 사용 안함)

\- 프록시 서버와 같은 중간 서버 경유

-터널링의 목적으로 연결을 요청함.

​     

⦁Get과 Post 차이점

\- Get은 주로 웹 브라우저가 웹 서버에 데이터를 요청할 때 사용

\- Post는 웹 브라우저가 웹 서버에 데이터를 전달하기 위해 사용.

\- Get을 사용하면 웹 브라우저에서 웹 서버로 전달되는 데이터가 인코딩되어 URL에 붙는다.

\- Post방식은 전달되는 데이터가 보이지 않는다.

\- Get방식은 전달되는 데이터가 255개의 문자를 초과하면 문제가 발생할 수 있다.

\- 웹서버에 많은 데이터를 전달하기 위해서는 Post 방식을 사용하는 것이 바람직하다.

​

{% if site.dispus-shortname %}{% include dispus.html %}{% endif %}