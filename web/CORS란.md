# CORS 교차 출처 리소스 공유
브라우저에서 실행 중인 스크립트에서 시작되는 cross-origin HTTP 요청을 제한하는 브라우저 보안 기능 <br/>
REST API의 리소스가 비 단순 cross-origin HTTP 요청을 받을 경우 CORS 지원을 활성화해야 함 <br/>
<br/>

cross-origin HTTP 요청은 다음에 대해 이루어지는 요청
* 다른 도메인(예: example.com에서 amazondomains.com으로)
* 다른 하위 도메인(예: example.com에서 petstore.example.com으로)
* 다른 포트(예: example.com에서 example.com:10777으로)
* 다른 프로토콜(예: https://example.com에서 http://example.com으로)

<br/>

### 단순 요청
= 예비 요청(preflight)을 생략할 수 있는 요청 
<br/>
<br/>
<b>필수 만족 조건 </b>
* GET/HEAD/POST 요청이며 
* 유저 에이전트가 자동으로 설정한 헤더외에, 수동으로 설정할 수 있는 헤더는 Fetch 명세에서 "CORS-safelisted request-header"로 정의한 헤더만 사용 
* Content-Type 을 사용하는 경우에는 text/plain, multipart/form-data, application/x-www-form-urlencoded 만 허용 

단순 cross-origin POST 메서드 요청의 경우 해당 리소스로부터의 응답에 Access-Control-Allow-Origin 헤더가 포함되어야 한다.
<br/> 헤더 키 값은 '*'(임의의 오리진)으로 설정되거나, 해당 리소스에 대한 액세스가 허용되는 오리진으로 설정됩니다. <br/>

단순요청은 예비 요청(Prefilght)을 보내지 않고 바로 서버에 직행으로 본 요청을 보낸 후, 서버가 이에 대한 응답의 헤더에 Access-Control-Allow-Origin과 같은 같을 보내주면 브라우저가 CORS정책 위반여부를 검사하는 방식

### 비단순 요청
다른 모든 cross-origin HTTP 요청은 비 단순 요청입니다. API의 리소스에서 비 단순 요청을 수신하는 경우 CORS 지원을 활성화해야 한다. <br/>

<br/>
<br/>

브라우저에서 비 단순 HTTP 요청을 받을 경우 CORS 프로토콜은 브라우저에 preflight 요청을 서버로 보내고, 
서버 승인(또는 자격 증명에 대한 요청)을 기다린 후 실제 요청을 보내도록 요구 <br/>

> <b>preflight 요청</b> <br/>
> Origin 헤더를 포함 <br/>
> OPTIONS 메서드를 사용 <br/>
> Access-Control-Request-Method, Access-Control-Request-Headers 헤더를 포함 <br/>

<br/>

### CORS 기본 동작 과정
1. 클라이언트에서 HTTP요청의 헤더에 Origin을 담아 전달
2. 서버는 응답헤더에 Access-Control-Allow-Origin을 담아 클라이언트로 전달
3. 클라이언트에서, 자신이 보냈던 요청의 Origin과 서버가 보내준 Access-Control-Allow-Origin을 비교 → 자신이 보낸 Origin과 서버가 보내준 Access-Control-Allow-Origin을 비교하여 차단할지 말지를 결정, 만약 유효하지 않다면 그 응답을 사용하지 않고 버림

<br/>

> ❕서버 응답은 CORS정책 위반 여부에 관여하지 않음 <br/>
> CORS 정책에 의해 Origin을 비교하는 로직은 브라우저에 구현되어 있다. <br/>
> 그래서 서버에서 정상적인 응답을 하여 상태코드가 200이 나오더라도, 브라우저가 응답을 CORS정책 위반이라고 분석하면 그 응답은 사용하지 않는다.  <br/>
> 브라우저가 CORS정책 위반을 분석하는 시간은 서버의 응답이 도착한 이후이다. <br/>