
## Q1. Spring MVC 사용이유에 대해 말해주세요.
### A1.
Spring MVC는 HTTP Request를 처리하는 부분인 Controller, 데이터를 처리해 정제된 데이터를 넣는 Model, 
정제된 데이터를 활용해 사용자에게 보여지는 View에 대한 역할 분리를 잘 해놓았다. 
Spring MVC 패턴을 사용하면 Model, View, Controller 모두를 인터페이스를 사용해 규격화해놓아 유연하고 확장성 있게 웹 어플리케이션을 설계할 수 있다.

</br>

## Q2. Spring Web MVC의 Dispatcher Servlet의 동작 원리에 대해서 간단히 설명해주세요.
### A2.
- DispatcherServlet은 Spring MVC의 가장 중요한 요소로 모든 클라이언트의 요청을 가장 먼저 받아들이는 역할을 수행합니다. 
- 즉, 사용자의 요청을 가장 먼저 받아 요청에 알맞는 Handler, Controller에 위임해주는 역할입니다. 

1. 클라이언트의 요청을 dispathcer servlet이 받음
2. HandlerMapping을 통해 요청을 처리할 Controller를 검색합니다.
3. 검색 된 Controller를 실행하여 클라이언트의 요청을 처리합니다. 
4. Controller는 비즈니스 로직을 수행하고 , ModelAndView 객체를 리턴합니다.
5. ModelAndView로부터 View 정보를 추출하고, ViewResolver를 이용하여 응답으로 사용할 view를 얻습니다.
6. View를 실행하여 응답을 전송합니다. 

</br>
</br>
</br>

# Spring MVC 프레임워크와 구조
### 1. Spring MVC
- Spring에서 제공하는 웹 모듈로, Model, View, Controller 세가지 구성요소를 사용해 사용자의 다양한 HTTP Request를 처리하고 
  단순한 텍스트 형식 응답부터 REST 형식의 응답, View를 표시하는 html을 return하는 응답까지 다양한 응답을 할 수 있는 프레임 워크
- 다양한 요쳥을 처리하고 응답하기 위해 주요 구성요소들을 만들어놓고 구성요소들을 확장할 수 있게 만들어 놓음

>  ![](https://velog.velcdn.com/images/ilov-/post/530888e3-d0e6-42ce-8049-db9ee04fccd5/image.png)

</br>

### 2. 구조

**DispatcherServlet(Front Controller)**
- 서블릿 컨테이너에서 http 프로토콜을 통해 들어오는 모든 request에 대해 제일 앞단에서 중앙집중식으로 처리해주는 핵심적인 역할
(앞쪽에서 처리하는 컨트롤러를 두는 패턴 : Front Controller 패턴)

**HandlerMapping**
- 클라이언트의 request url을 어떤 컨트롤러가 처리해야 할 지 찾아서 Dispatcher Servlet에게 전달해주는 역할
- 컨트롤러 상에서 url을 매핑시키기 위해 @RequestMapping을 사용하는데, 핸들러가 이를 찾아줌

**Handler(Controller)**
- HTTP Request를 처리해 Model을 만들고 HTTP가 보여줄 View Name을 지정
- 실질적인 요청을 처리하는 곳이고, Dispatcher Servlet이 프론트 컨트롤러라면, 이 곳은 백엔드 컨트롤러라고 볼 수 있음
- Model의 처리 결과를 담아 Dispatcher Servlet에게 반환

**ModelAndView**
- Controller에 의해 반환된 Model과 View가 Wrapping된 객체
- View가 지정되더라도 데이터가 세팅된 View가 지정되지 않음

**ViewResolver**
- String 형태로 넘어온 viewName을 받고, Model에 저장된 데이터를 사용해 View 객체 생성
- 컨트롤러의 처리 결과를 만들 view를 결정해주는 역할

**View**
-  모델과 viewName 받아서 화면에 그려주는 역할 수행

</br>


> [Spring MVC 과정](https://velog.io/@miscaminos/Spring-MVC-framework)
