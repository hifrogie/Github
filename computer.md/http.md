## 1. HTTP 통신
### 1. HTTP(Hyper Text Transfer Protocol) 
1. 웹 브라우저와 웹 서버가 HTML로 작성된 웹 페이지나 동영상, 음성 파일 등등을 주고받기 위한 프로토콜(통신규약)입니다. 
2. HTTP에서는 클라이언트가 서버에 요청 메세지를 보내고 이에 대해 서버가 응답 메세지를 반환합니다.
![클라이언트](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F2uDtD%2FbtqEepoz93p%2FNdnyQBPeYLS18pxzO32xck%2Fimg.jpg)

### 2. HTTP 프로토콜의 특징
1. 서버는 응답 메세지를 반환한 후에 초기상태로 돌아갑니다. 이 때 서버는 클라이언트의 상태를 저장하지 않습니다.
2. 즉, HTTP 프로토콜은 상태가 없는 프로토콜 입니다. 상태가 없다는 말은 데이터를 주고 받기 위한 각각의 데이터 요청이 서로 독립적으로 관리가 된다는 말이고, 이전 데이터 요청과 다음 데이터 요청이 서로 관련이 없다는 말이다.
3. 이러한 특징 덕분에 서버는 세션과 같은 별도의 추가 정보를 관리하지 않아도 되고, 다수의 요청 처리 및 서버의 부하를 줄일 수 있는 성능 상의 이점이 생깁니다.

### 3. HTTP 통신의 동작 순서
1. 주소창에 URL을 입력 후 엔터를 치면 URL을 해석
2. DNS(도메인 이름 시스템은 사람이 읽을 수 있는 도메인이름을 머신이 읽을 수있는 IP주소로 변환합니다.)를 조회하여 IP 탐색
3. IP를 찾아 해당 IP가 존재하는 서버로 이동
4. ARP(Address Resolution Protocol은 네트워크 상에서 IP 주소를 물리적 네트워크 주소로 대응시키기 위해 사용되는 프로토콜)을 이용하여 MAC 주소(Media Access Control Address 네트워크 통신을 하는 하드웨어에 할당된 주소 )로 변환
    - 하드웨어 : 컴퓨터의 물리적 부품
5. 웹서버와 TCP(Transmission Control Protocol은 컴퓨터와 데이터 통신을 위한 규약의 일종) 연결 시도
6. 서버에 요청을 하고 응답을 반환
7. 연결 종료

### 4. HTTP messages
1. HTTP messages란?
    - 클라이언트와 서버 사이에서 데이터가 교환되는 방식
2. HTTP messages 두 가지 유형
    - 요청(Requests)
    - 응답(Responses)
3. HTTP message 구성
    - HTTP messages는 몇 줄의 텍스트 정보로 구성됩니다.
    - 그러나 개발자는 이런 메세지를 직접 작성할 필요가 거의 없다.
    - 구성 파일,API,기타 인터페이스에서 HTTP messages를 자동으로 완성한다.

### 5. 요청(Requests)과 응답(Responses)의 구조

![요청 이미지](https://velog.velcdn.com/images%2Fgparkkii%2Fpost%2F531ed3d6-a210-4c97-ac23-00aaf9926436%2FHTTPMsgStructure2.png)

1. HTTP 요청 메세지(Request)

  ![요청 메세지](https://velog.velcdn.com/images%2Fgparkkii%2Fpost%2F0a8a066b-b53b-4c86-a522-32e848c5f54f%2FHTTP_Request.png)

1. Method : HTTP메서드는 보통 클라이언트가 수행하고자 하는 동작을 정의한 GET,POST,OPTIONS,HEAD를 지칭한다. 클라이언트 리소스를 가져오거나 GET 사용 HTML 폼의 데이터를 전송 POST 사용한다. 다른 경우에는 다른 동작이 요구될 수도 있다.
2. Path : 가져오려는 리소스의 경로는 프로토콜 http://,도메인(developer.mozilla.org),또는 TCP 포트인 요소들을 제거한 리소스의 URL이다.
3. Version of the Protocol : HTTP 프로토콜의 버전
4. Headers : 서버에 대한 추가 정보를 전달하는 선택적 헤더들/
5. etc : POST와 같은 몇 가지 메서드를 위한, 전송된 리소스를 포함하는 응답의 본문과 유사한 본문.
 
 
  ![응답 메세지](https://velog.velcdn.com/images%2Fgparkkii%2Fpost%2Fc5ee6879-e3af-49f9-a8d0-5922b49c53ce%2FHTTP_Response.png)

2. HTTP 응답 메세지(Response)

    1. Version of the Protocol : HTTP 프로토콜의 버전
    2. Status Code : 요청의 성공 여부와, 그 이유를 나타내는 상태 코드.
    3. Status Message : 아무런 영향력이 없는, 상태코드의 짧은 설명을 나타내는 상태 메세지.
    4. Headers : 요청 헤더와 비슷한, HTTP 헤더들.
    5. etc : 선택 사항으로, 가져온 리소스가 포함되는 본문.

### 6. HTTP 메세지 구조

![메시지 구조](https://velog.velcdn.com/images%2Fgparkkii%2Fpost%2Fa8c0793f-86bf-4744-8d83-56c457c00b2f%2Ftip_20070425_1.jpg)

1. 요청메세지 시작라인 : GET/search?q=hello&hl=ko HTTP/1.1
    - 요청 라인 = request line
    - method : HTTP 메서드(Get:조회)
        - HTTP 메서드
            - 종류 : GET(리소스 조회),POST(요청 내역 처리),PUT,DELETE
            - 서버가 수행해야할 동작 지정
    - Request-target:요청대상(/search?q=hello&hl=ko)
        - Request-Target
            - absolute-path?query
            - 절대경로 ="/"로 시작하는 경로
    - HTTP Version(HTTP 1.1)


![응답라인](https://velog.velcdn.com/images%2Fgparkkii%2Fpost%2F5ee3b2f9-ce42-41f2-bb3e-f3bc3c146e1f%2F%E1%84%8B%E1%85%B3%E1%86%BC%E1%84%83%E1%85%A1%E1%86%B8%E1%84%86%E1%85%A6%E1%84%89%E1%85%B5%E1%84%8C%E1%85%B5.png)

2. 응답 메세지 시작라인
    - 응답 라인 = status line
    - 응답 라인 시작 라인 : HTTP/1.1 200 OK
    - HTTP Version
    - HTTP 상태코드 : 요청 성공, 실패를 나타냄
        - 200:성공
        - 400:클라이언트 요청 오류
        - 500:서버 내부 오류
    - 이유 문구 : 사람이 이해할 수 있는 짧은 상태 코드 설명 글 

3. 헤더라인
    - HTTP 헤더
    
    /* rfc7230 공식스펙 */
    header-field = field-name ":" OWS field-value OWS (OWS:뛰어쓰기 허용)
    field-name 대소문자 구분 없음
    
    - 요청 메세지 헤더: Host:www.google.com
    - 응답 메세지 헤더:
        Content-type: text/html;charset=UTF-8
        Content-Length: 3423
    - HTTP 헤더의 용도
        - HTTP 전송에 필요한 모든 부가정보가 들어있다.
        - 표준 헤더가 너무 많다.
        - 필요시 임의의 헤더도 추가할 수 있다.
4. 메시지 바디
    < HTML >
  < body >...</ body >
    </ HTML >

    - 실제 전송할 데이터이다.
    - HTML 문서, 이미지 ,영상 JSON 등등 byte로 표현할 수 있는 모든 데이터가 전송 가능하다.

### 7. Get,Post 데이터 전송 방식
1. Get 방식
    1. ex) http://khj93.tistory.com/test_api?param1=value1&param2=value2 
    2. URL에 Parameter를 붙여서 전송한다는 것
    3. URL 뒤에 ?를 사용하여 Parameter를 작성하게 되고 &을 붙여 여러개의 Parameter를 구분하게 됩니다.
    4. GET방식은 데이터를 전송하게 되면 URL에 Parameter를 전송하기 때문에 body영역을 사용하지 않는다.
    5. URL에 데이터를 실어 보내기 때문에 대용량 데이터 전송을 하기에 제한 사항이 있다.
    6. 한 번 요청시 URL 포함 255자 까지 전송이 가능하며 HTTP/1.1에서는 2048 까지 가능합니다.

2. POST 방식
    1. body영역에 데이터를 실어 보낸다는 점
    2. body에 데이터를 실어 보내기 때문에 데이터 전송양에 길이 제한이 없으며 대용량 데이터를 보내는데 적합합니다.
    3. POST로 데이터를 전송할 때는 Body영역 데이터 타입을 Header Content-Type에 명시를 해줘야 합니다. 
    4. POST방식은 GET 방식과는 달리 보내는 데이터를 URL을 통해 볼수 없어 보안적으로 안전하다고 하지만 다른 툴을 사용하여 데이터를 확인할 수 있다.

3. GET 방식과 POST방식의 차이
1. GET방식은 idempotent, POST 방식은 non-idempotent
2. idempotent는 멱등성으로서 수학적으로 연산을 여러번 적용하더라도 결과 값이 바뀌지 않는다는 성질
3. GET메소드를 사용해서는 여러번 적용하더라도 결과 값이 바뀌지 않는 것을 개발하고 POST메소드를 사용해서는 결과값이 바뀌는 유형의 개발이 적합하다.

### 8. 컴퓨터 네트워크
1. 컴퓨터 네트 워크 : 컴퓨터 간 데이터를 교환할 수 있는 통신 네트워크(망)
2. internet(internetworking) 
    - 네트워크의 네트워크라는 의미 
    - TCP/IP 프로토콜로 컴퓨터 네트워크를 연결하여 만든 네트워크
3. 네트워크 프로그래밍 : 컴퓨터 네트워크를 이용하여 컴퓨터간 데이터를 교환할 수 있도록 주고받는 규칙을 만들고 그 규칙에 따라 컴퓨터가 데이터를 처리하도록 만드는 작업
4. 네트워크 종류
   - LAN(Local Area Network) : 네트워크 매체를 이용하여 집, 사무실, 학교와 같은 가까운 지역을 한데 묶는 컴퓨터 네트워크

