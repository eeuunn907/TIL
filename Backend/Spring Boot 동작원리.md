### Spring Boot 동작원리

***
스프링 부트의 기본 의존성 중 하나인 **spring-boot-starter-web** 모듈을 사용하면, 
기본적으로 내장 톰캣(Tomcat)을 사용하는 스프링 **MVC 구조를** 기반으로 동작한다. 

>서블릿(Servlet)은 클라이언트의 요청을 처리하고, 결과를 반환하는 자바의 웹 프로그래밍 기술이다.

###### 서블릿 컨테이너의 특징 <br>

-   서블릿 객체를 생성,초기화,호출,종료하는 **생명주기**를 관리한다
-   서블릿 객체는 **싱클톤 패턴**으로 관리된다.
-   멀티 스레딩을 지원한다.

### Dispatcher Servlet 이란? <br>
스프링에서는 DispatcherServlet이 서블릿의 역할을 담당한다.

클라이언트의 요청을 받아서 서블릿 컨테이너에서 관리되는 DispatcherServlet이 요청을 처리하고 반환하는 것이다.

### DispatcherServlet의 동작
https://innovation123.tistory.com/168

1. 클라이언트 요청 <br>
   클라이언트에서 요청(HttpServletRequest)이 들어오면, 서블릿 컨테이너는 DispatcherServlet으로 이를 전달한다.


2. Handler 조회 <br>
   DispatcherServlet은 핸들러 매핑(HandlerMapping)을 통해 요청 URI에 매핑된 핸들러(Controller)를 탐색한다.


3. Handler Adapter 조회  <br>
   조회한 핸들러를 실행할 수 있는 핸들러 어댑터를 조회한다.


4. Handler Adapter 실행  <br>
   핸들러 어댑터(HandlerAdapter)를 통해 핸들러(Controller)를 호출한다.


5. Handler(Controller) 실행 <br>
   핸들러(Controller)를 실행하여 컨트롤러에서 요청을 처리하고, 응답을 다시 핸들러 어댑터로 반환한다.


6. ModelAndView 반환  <br>
   핸들러 어댑터는 이 응답을 ModelAndView로 가공하여 반환한다.


7-1. @Controller 사용 시  <br>
1) View Resolver를 찾고 실행한다.

2) View Resolver는 View의 논리 이름을 물리 이름으로 바꾸고, 랜더링 역할을 담당하는 View 객체를 반환한다.

3) View를 랜더링 하여 클라이언트에 반환한다.

7-2. @RestController 사용 시  <br>
1) View와 ViewResolver를 거치지 않는다.

2) Controller로 부터 반환 받은 데이터를 MessageConverter를 거쳐서 Json 형식으로 변환한다.

3) Json을 ResponseBody로 응답한다.