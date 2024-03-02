### REST란?
1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
2. HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미합니다.

**CRUD Operation이란** <br>
CRUD는 대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말로
REST에서의 CRUD Operation 동작 예시는 다음과 같다.

+ Create : 데이터 생성(POST) <br>
+ Read : 데이터 조회(GET) <br>
+ Update : 데이터 수정(PUT, PATCH) <br>
+ Delete : 데이터 삭제(DELETE) <br>

## REST 구성 요소

REST는 다음과 같은 3가지로 구성이 되어있다.

1. 자원(Resource) : HTTP URI
2. 자원에 대한 행위(Verb) : HTTP Method
3. 자원에 대한 행위의 내용 (Representations) : HTTP Message Pay Load

**HTTP Method** <br>
클라이언트가 서버로 요청을 할 때, 어떠한 목적을 갖는 행위인지 HTTP 메서드에 명시합니다.

+ GET
    + 서버에게 리소스를 달라는 요청 ( 조회 ) <br>
+ HEAD <br>
    + 정확히 GET과 같지만, 서버는 응답으로 엔터티 본문 반환없이 헤더만을 반환.
    클라이언트는 리소스를 가져올 필요 없이 헤더만을 통해 정보를 얻을 수 있습니다.
+ PUT <br>
  + 자원의 전체 교체, 자원교체 시 모든 필드 필요 ( 수정 )
  + 만약 전체가 아닌 일부만 전달할 경우 , 전달한 필드 외 모두 null or 초기화 처리되니 주의 
+ POST <br>
  + 서버에 입력데이터를 전송하며 요청 엔티티 본문에 데이터를 넣어 서버에 전송합니다. ( 삽입 )
+ DELETE <br>
  + 서버에서 요청 URI 리소스를 삭제하도록 요청합니다. ( 삭제 ) <br>
클라이언트는 항상 삭제된다고 생각하지만, 서버에서는 이 요청을 무시할 수도 있습니다.

+ PATCH <br>
  + 자원의 부분 교체, 자원교체시 일부 필드 필요 (수정)

+ TRACE <br>
  + 클라이언트와 목적지 서버 사이에 있는 모든 HTTP 애플리케이션의 요청/응답 연쇄를 따라가면서 자신이 보낸 메시지의 이상 유무를 파악합니다.
서버는 응답 메시지의 본문에 자신이 받은 요청메시지를 넣어 응답하며, 주로 진단을 위해 사용합니다.
+ OPTIONS <br>
  + 서버에게 특정 리소스가 어떤 메소드를 지원하는지 물어볼 수 있습니다.



**REST의 특징**

1. Server-Client(서버-클라이언트 구조)
2. Stateless(무상태)
3. Cacheable(캐시 처리 가능)
4. Layered System(계층화)
5. Uniform Interface(인터페이스 일관성)


**REST의 장단점** <br>

장점
+ HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출할 필요가 없다.
+ HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해 준다.
+ HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
+ Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
+ REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
+ 여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
+ 서버와 클라이언트의 역할을 명확하게 분리한다.


단점
+ 표준이 자체가 존재하지 않아 정의가 필요하다.
+ HTTP Method 형태가 제한적이다.
+ 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구된다.
+ 구형 브라우저에서 호환이 되지 않아 지원해주지 못하는 동작이 많다.(익스폴로어)
