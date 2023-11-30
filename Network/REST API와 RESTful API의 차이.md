## REST API와 RESTful API의 차이

```

REST의 설계 규칙을 잘 지켜서 설계된 API를 RESTful한 API라고합니다.
설계 규칙에는 URI는 리소스를 표현해야 하며 명사를 사용하고, 슬래시로 계층 관계를 표현할 것, 소문자로만 구성할 것 등이 있고
자원에 대한 행위는 HTTP Method로 표현해야하며 HTTP 응답 코드로 클라이언트에게 피드백을 해줘야 한다는 것입니다.

```

### REST
어떤 자원에 대해 CRUD(Create, Read, Update, Delete) 연산을 수행하기 위해

URI(Resource)로 GET, POST 등의 방식(Method)을 사용하여 요청을 보내며,

요청을 위한 자원은 특정한 형태(Representation of Resource)로 표현

### REST API
REST의 특징을 기반으로 서비스 API를 구현한 것

#### 설계 규칙

1. URI는 명사를 사용할 것
    - 동사를 사용하지 말라는 얘기=> 예시 : `/getUsers, /createNewUser`
2. 슬래시( / )로 계층 관계를 표현할 것
    - 예시 : `/review/comment`
3. URI 마지막 문자로 슬래시( / )를 포함하지 말 것
4. 밑줄( _ )을 사용하지 말고 하이픈( - )을 사용할 것
5. URI는 소문자로만 구성할 것
6. HTTP 응답 상태 코드 사용할 것
    - 클라이언트는 해당 요청에 대한 실패 처리완료, 잘못된 요청 등에 대한 피드백 필요
    - 2xx은 성공 / 4xx은 클라이언트 실패 / 5xx은 서버 실패
7. 파일확장자는 URI에 포함하지 않는다.
