## HTTP 란?
1. HTTP(hyper-text transfer protocol, 하이퍼본문전송규약)
2. HTTP 요청 메세지
3. HTTP 응답 메세지
4. HTTPS(HyperText Transfer Protocol over Secure Socket Layer)
5. 소켓 통신이란
---

### HTTP(hyper-text transfer protocol, 하이퍼본문전송규약)
- 웹 상에서 클라이언트와 서버 간에 요청/응답(request/response) 규칙이다.
- 주로 HTML 문서를 주고받는 데에 쓰인다.
- TCP와 UDP를 사용하며, 80번 포트를 사용한다.
- TCP 위에서 동작하지만 TCP와는 달리 무상태성 혹은 비연결성이다. 때문에 쿠키나 세션을 이용하여 클라이언트의 상태를 관리할 수 있다.
- 비연결(Connectionless) : 클라이언트가 요청을 서버에 보내고 서버가 적절한 응답을 클라이언트에 보내면 바로 연결이 끊긴다.
- 무상태(Stateless) : 연결을 끊는 순간 클라이언트와 서버의 통신은 끝나며 상태 정보를 유지하지 않는다.

### HTTP 요청 메세지
```
GET /restapi/v1.0 HTTP/1.1
Accept: application/json
Authorization: Bearer UExBMDFUMDRQV1MwMnzpdvtYYNWMSJ7CL8h0zM6q6a9ntw
(empty line)
본문
```
- 요청 내용 : GET /images/logo.gif HTTP/1.1
- 헤더 : Accept-Language: en
- 빈 줄 (empty line)
- 본문 : 함께 전송할 데이터가 표시된다.

### HTTP 응답 메세지
```
HTTP/1.1 200 OK
Date: Mon, 23 May 2005 22:38:34 GMT
Content-Type: text/html; charset=UTF-8
Content-Encoding: UTF-8
Content-Length: 138
Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux)
ETag: "3f80f-1b6-3e1cb03b"
Accept-Ranges: bytes
Connection: close

<html>
<head>
  <title>An Example Page</title>
</head>
<body>
  Hello World, this is a very simple HTML document.
</body>
</html>
```
- 상태표시 행(status line): 상태코드(status code)와 reason message를 포함한다. (예. HTTP/1.1 200 OK. 클라이언트의 요청이 성공적으로 전달되었음을 표시)
- 응답 헤더필드 (예.Content-Type: text/html)
- 빈 줄 (empty line)
- 본문 : 함께 전송할 데이터

### HTTPS(HyperText Transfer Protocol over Secure Socket Layer)
- HTTPS에서 통신 프로토콜은 TLS(Transport Layer Security) 또는 이전에는 SSL(Secure Sockets Layer)을 사용하여 암호화된다. 따라서 "HTTP over TLS" 또는 "HTTP over SSL" 이라고도 불린다.
- HTTPS의 기본 TCP/IP 포트는 443이다.
- 보호의 수준은 웹 브라우저에서의 구현 정확도와 서버 소프트웨어, 지원하는 암호화 알고리즘에 달려있다.
- HTTPS 웹사이트가 SSL/TLS 인증서로 보호되는 경우 HTTPS가 URL에 표시됩니다. 사용자는 브라우저 표시줄의 자물쇠 기호를 클릭해 발급 기관 및 웹사이트 소유자의 상호를 포함한 인증서의 세부 정보를 볼 수 있습니다.

### TSL(SSL)이란
- SSL: 보안 소켓 계층(Secure Sockets Layer) 인증서는 종종 디지털 인증서로 불리며, 브라우저(사용자의 컴퓨터)와 서버(웹사이트) 사이의 암호화된 연결을 수립하는 데 사용됩니다.
- TLS: 전송 계층 보안(Transport Layer Security) 은 SSL의 향상된, 더욱 안전한 버전입니다. SSL 및 TLS는 본질적으로 같으며 버전이 다른 정도입니다.
- 대칭키 : 암호화에 쓰이는 키와 복호화에 쓰이는 키가 동일한 기법입니다.
- 공개키(비대칭키) : 공개키와 개인키(비밀키)라는 2가지 키를 사용하는 기법입니다.
- 인증서와 CA(Certificate authority) : SSL을 적용하기 위해서는 인증서라는 것이 필요합니다.이 인증서를 발급해주는 기업을 CA라고 합니다. 인증서가 보안에 관련된 것인 만큼 이 CA는 영향력있고 신뢰할수 있는 기업에서만 가능합니다. 그리고 우리의 브라우저는 CA리스트를 미리 가지고 있습니다. CA목록에 있는 기업을 공인된 CA라고 합니다.
- HTTPS 동작방식 : 대칭키와 공개키(비대칭키) 방식을 전부 사용하는 하이브리드 방식입니다. 데이터 전송을 위해 대칭키 방식을 사용하며 대칭키를 안전하게 전달하기 위해 공개키 방식을 사용합니다.

### 소켓 통신이란
- Socket 연결은 TCP/IP 프로토콜을 기반으로 맺어진 네트워크 연결 방식이다.
- HTTP 연결은 TCP/IP 연결을 기반으로 하므로 기본적으로 소켓 연결 위에서 맺어지는 애플리케이션 계층의 연결 방식이다.
- Http 프로그래밍 : Client만 필요한 경우에 요청을 보낼 수 있다.
- Socket 프로그래밍 : Server 역시 Client로 요청을 보낼 수 있으며, Server와 Client가 특정 Port를 통해 연결을 유지하고 있어 실시간으로 양방향 통신을 할 수 있다.

---
reference
- https://ko.wikipedia.org/wiki/HTTP
- https://www.zerocho.com/category/HTTP
- https://bitcodic.tistory.com/151
- https://mangkyu.tistory.com/48 
- https://mysterico.tistory.com/29
- https://mysterico.tistory.com/30
- http://www.ktword.co.kr/test/view/view.php?m_temp1=1957
- https://doozi0316.tistory.com/entry/HTTPHTTPS%EB%9E%80-TCP-UDP-HandShake-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC
