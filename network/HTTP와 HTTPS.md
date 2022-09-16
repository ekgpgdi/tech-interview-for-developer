# HTTP vs HTTPS?<br>
###  HTTP (Hyper Text Transfer Protocol)
: **서버/클라이언트 모델을 따라 데이터를 주고 받기 위한 프로토콜** <br>
→ HTTP는 인터넷에서 하이퍼텍스트를 교환하기 위한 통신 규약, 80번 포트 사용<br> 따라서 HTTP 서버가 80번 포트에서 요청을 기다리고 있으며, 클라이언트는 80번 포트로 요청을 보내게 된다.
###  HTTPS (HyperText Transfer Protocol over 'Secure Socket Layer')
: HTTP에 **데이터 암호화**가 추가된 프로토콜 (443번 포트) <br>
→ 인터넷 상에서 정보를 암호화하기 위해 SSL 프로토콜을 이용해 데이터를 전송하고 있다는 것을 말함. <br>
→ SSL 프로토콜은 정보를 암호화시키고 이때 '공개키'와 '개인키' 두가지를 이용함<br>


<br>

#### ➡︎ HTTP와 HTTPS의 차이
- HTTP는 암호화가 추가되지 않았기 때문에 보안에 취약한 반면, HTTPS는 안전하게 데이터를 주고받을 수 있다. <br> 하지만 HTTPS를 이용하면 암호화/복호화의 과정이 필요하기 때문에 HTTP보다 속도가 느리다. (오늘날에는 거의 차이를 못느낄 정도)<br> 또한 HTTPS는 인증서를 발급하고 유지하기 위한 추가 비용이 발생하다.
#### ➡︎ 그렇다면 언제 HTTP를 쓰고, 언제 HTTPS를 쓰는 것이 좋겠는가?
- 개인 정보와 같은 민감한 데이터를 주고 받아야 한다면 HTTPS를 이용해야 하지만, <br>노출이 되어도 괜찮은 단순한 정보 조회 등 만을 처리하고 있다면 HTTP를 이용하면 된다.
#### ➡︎ 동작순서 차이
- HTTP 동작 순서 : TCP → HTTP
- HTTPS 동작 순서 : TCP → SSL → HTTP
> SSL(Secure Socket Layer)을 쓰냐 안쓰냐의 차이 

즉, **문서 전송시 암호화 처리 유무**에 따라 HTTP와 HTTPS로 나누어지는 것.<br>
모든 사이트가 HTTPS로 하지 않는 이유는, 암호화 과정으로 인한 **속도 저하**가 발생하기 때문이다.

<br><br><br>

#### 출처

[https://mangkyu.tistory.com/98](https://mangkyu.tistory.com/98)<br>
[https://gyoogle.dev/blog/interview/네트워크.html](https://gyoogle.dev/blog/interview/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC.html)
