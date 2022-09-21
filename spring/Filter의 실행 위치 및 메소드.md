## Filter 란?
필터는 스프링의 독자적인 기능이 아닌 자바 서블릿에서 제공하는 기능 <br/>
<br/>
스프링 프레임워크는 들어온 요청이 DispatcherServlet에 의해 컨트롤러에 매핑 <br/>
Filter는 요청이 <b>DispatcherServlet에 의해 다뤄지기 전, 후</b>에 동작 <br/>
<br/>
Filter는 FilterChain(필터 체인)을 통해 여러 필터가 연쇄적으로 동작하게 할 수 있음 <br/>
<br/>

### Filter 의 메소드 
1. init() : 필터 가 생성될 때 수행되는 메소드
2. doFilter() : Request, Response가 필터를 거칠 때 수행되는 메소드
3. destroy() : 필터가 소멸될 때 수행되는 메소드