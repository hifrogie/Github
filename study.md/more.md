## 1. 더 공부할 것
### 1. 1일
1. 컴파일과 빌드의 차이 설명
2. 클래스변수(static)이 위험한 이유 (잘못된 사용사례)
3. Pass By Reference가 왜 사용되는지?
4. 접근제어자가 왜 중요한지, 객체지향의 개념을 연관지어서 설명
- 자료구조가 무엇이고, 왜 중요한가? 대표적으로 어떤 자료구조들이 있으며, 각각의 특징과 동작방식은 무엇인가?
### 2. 다형성
1. 다형성에 대해서
2. 동일성 vs 동등성이 무엇인가?
3. equals, hashCode가 왜중요한지, 차이점, 어떻게 구현하는지?
4. enum 클래스의 메모리 구조. (어떻게 적재되는지?)
### 3. equals()
1. equals, hashCode가 왜 중요한지? 어떻게 구현하는지?, 구현하지 않으면 어떤 문제가 있는지?
- Effective Java 아이템 10,11 참고
2. enum, 싱글톤패턴의 차이
3. checked, unchecked 에외의 차이 설명. 어떻게 사용하는가?
- HTTP 통신은 무엇이며 동작 흐름이 어떻게 되는가?
### 4. inner 클래스
1. inner클래스와 nested클래스의 차이. inner클래스에서 어떻게 외부클래스의 멤버/메서드를 사용할 수 있을까?. 이로인해 발생할 수 있는 문제는 무엇일까?
2. 메타데이터(metadata)의 의미
3. 인터페이스의 메서드 구현체를 어떻게 넣을 수 있는가?
4. 디폴트(default) 메서드에 대해서 조사
- HTTP 요청/응답메시지 구조에 대해서 조사
- 헤더 / 바디
- 요청 헤더 / 응답 헤더에는 어떤 내용들이 들어가는지?
- HTTP에서 메서드는 무엇인지?
- StatusCode는 무엇인지? 등등
### 5. 메모리 구조
1. 프로그램의 메모리 구조에 대해서
2. 시간/공간복잡도
3. ArrayList, LinkedList 차이
4. Stack이 Vector를 상속받아서 망한 이유
5. Hash가 무엇인가?
6. HashMap, Hashtable, ConcurrentHashMap
- 운영체제(OS)는 무엇인가요? 컴퓨터에서 어떤 일을 하나요?
- GET, POST 데이터전송 방식
### 6. hash
1. Hash가 무엇인지? Hash방식, Hash 충돌해결
2. 프로세서(코어) 스레드의 관계
3. 프로세스와 스레드의 구조, 관계
4. 상대경로, 절대경로
5. 블로킹(Blocking) IO vs 논블로킹(non-blocking) IO
- 프로세스는 무엇인가? 프로세스와 스레드의 차이는?
- 운영체제에서는 프로세스와 스레드를 어떻게 다루는가? (운영체제의 관점으로 조사하기)
### 7. when
1. when, switch의 차이 (화면공유로 같이 코드 보기)
2. in 키워드 조사 (화면공유로 같이 코드 보기)
- 객체지향 설계원칙 SOLID는 무엇인가?
### 8. data class
1. data class 조사 (화면공유로 같이 코드 보기)
2. copy()가 언제/왜 사용되는지?
3. object가 static 메모리에 언제 적재되는지
4. with, apply, also, let, run (내부구조 살펴보기)
- SOLID의 예제코드를 찾아보고, 설명 준비하기
### 9. android
1. data class에서 자동생성되는 equals(), hashCode()의 구현내용 조사하기
2. with, apply, also, let, run 내부구조 코드보면서 설명하기
3. Gradle 역할
4. 안드로이드 4대 컴포넌트 역할 설명하기
5. 엑티비티, 프레그먼트 생명주기 이해하고 설명하기
- Dalvik, ART가 무엇인지? 차이 조사하기
### 10. layout
1. RelativeLayout과 ConstraintLayout의 차이 조사. ConstraintLayout 많이 사용해보기
2. ANR 조사
3. jetpack 라이브러리가 뭔지? 어떤 내용들이 있는지?
### 11. view
1. View가 화면에 그려지기까지의 플로우. (onMeasure , onLayout , onDraw)
2. MVC, MVP, MVVM, Clean Architecture 패턴은 무엇인가요? (각 패턴 비교, 구조 파악하기)
### 12. lateinit
1. by lazy()와 lateinit의 차이
- 안드로이드에서 데이터를 영구적으로 저장하는 방법은 어떤것들이 있나요? 각각의 장단점은 어떤가요?
### 13. tree
- 트리는 무엇인가요? 이진트리, B트리는 무엇이고, 어떻게 사용하나요? (자세히)
### 14. graph
1. 메모리 릭과 자바의 Reference 객체 (WeakReference, SoftReference..)를 연관지어 설명하기 - 가비지컬렉션과 연관되어 질문이 나올 수 있음
- 그래프는 무엇인가요? 언제 사용하나요?
### 15. DFS
- DFS, BFS 조사하기
### 16. tdd
- 테스트코드는 무엇이고 왜 중요한가요? 어떤 종류가 있나요?, TDD는 무엇인가요?
### 17.activity
- Activity
### 18. 모의 면접
1. 배열과 리스트에 대해서 설명을 잘 하지 못함
2. 면접관의 피드백(힌트)을 듣고 캐치하는 능력이 필요해 보임.
3. 이진트리에 대해서는 어느정도 기억을 하는것으로 보이나, 자세히 질문하면 막힘
4. hashCode()에 대해 잘못알고 있음
5. Throwable, Error, Exception의 차이를 잘 모름
6. 자바와 코틀린의 차이에 대해 분명히 알아야 함. - 코틀린의 강점!
7. 고차함수에서 inline에 대해서 제대로 이해하지 못하고 있음
8. 확장함수에 대해 잘못 이해하고 있음
9. Java - Object
- Object 클래스에 대해 설명
- 어떤 메서드가 존재하는가?
- equals()의 기능은?
- equals()를 오버라이드하려면 반드시 같이 오버라이드 해야하는 메서드는?
10. Java - Throwable
- Throwable, Error, Exception의 차이?
- Checked Exception, Unchecked Exception 설명
11. Kotlin - Data class
- 일반 클래스와의 차이점
- 확장함수
- 확장함수란? 설명
- 이미 컴파일된 클래스에도 함수를 추가하는게 가능한데, 자바클래스로 어떻게 변환되기에 가능할까?
- 고차함수
- 고차함수란? 설명
- 람다는 언제 객체화되는가?
- inline이란?
- inline 함수를 만들때 조심해야할 것?
12. CS - Tree
- 트리 자료구조 설명
- 이진트리 설명
- 이진트리는 언제 사용하는가?
- 이진트리의 시간복잡도
- 트리의 순회방법
13. CS - Array
- 배열과 리스트 차이
- 시간복잡도는?
- 각각 언제 사용되는게 좋을까?
### 19. fragment
- fragment
### 20. 정렬
- 정렬 알고리즘에 대해 공부하기
### 21. aac
1. ViewModel, LiveData에 대해 공부하고 프로젝트에 적용하기
2. LiveData의 경우, Observer 패턴을 먼저 공부해보면 도움 됨
### 22. handler
1. Handler, Message, MessageQueue, Looper, HandlerThread
- 코루틴 공식문서 - https://kotlinlang.org/docs/coroutines-overview.html
- 코틀린 동시성 프로그래밍(책) - http://www.yes24.com/Product/Goods/90338766
- 안드로이드 멀티스레딩(책) - http://www.yes24.com/Product/Goods/16669722
### 23. 제안
1. Navigation Component
2. Hilt
3. Sunflower 공부
- CI/CD는 무엇인가요? (Continuous Integration / Continuous Deployment)
### 24. 코틀린 멀티 플래폼 모바일
1. 코틀린 멀티플랫폼 모바일(Kotlin Multiplatform Mobile)
### 25. Jetpack Compose
- Jetpack Compose는 무엇인가요? 왜 도입되었을까요?

- 트렌드 확인 커뮤니티
- Android Weekly - https://androidweekly.net/
- 요즘IT - https://yozm.wishket.com/magazine/list/develop/
- Dev Community - https://dev.to/
- Android Dev Summit - https://developer.android.com/events/dev-summit

### 26. 앞으로 공부할 것
1. 자료구조
- 자료(데이터)를 효율적으로 메모리에 저장하기 위함
- 배열, 리스트, 스택, 큐, 트리, 그래프, 해시…
- 링크드리스트를 사용? 어레이을 사용? 해시를 사용? 트리를 사용?
2. 알고리즘
- 자료(데이터를) 효율적으로 가공하기 위함
- 정렬, 검색, 순회, 분할정복, 동적계획, 탐욕…
- 어떤 정렬을 사용해야 효과적일까? 문제를 어떻게 해결할 수 있을까?
3. 네트워크
- 실제적인 통신 방법의 원리를 알기 위함
- HTTP, TCP/IP, 라우팅…
- TCP, IP가 무엇인가? HTTP는 어떤 원리로 구현되었는가?
4. 데이터베이스
- 대규모의 데이터를 효율적으로 저장하고 관리하기 위함
- SQL, RDBMS, ORM…
- 메모리의 데이터를 어떤 DB를 이용하여 저장하면 빠를까?
5. 컴퓨터구조
- 컴퓨터가 어떻게 설계되어 있는지 알기 위함 (하드웨어)
- CPU, 메모리(RAM), IO(하드디스크)…
- 왜 파일로 저장하는게 느릴까?, CPU는 어떤 방식이지?
6. 운영체제
- 만든 프로그램(애플리케이션)이 컴퓨터에서(OS상에서) 더 효율적으로 동작하도록 하기 위함
- 프로세스, 스레드, 메모리, 스케쥴링, 캐시…
- 내가 만든 프로그램(프로세스)가 스레드를 어떻게 해야 잘 사용할까? 왜 OutOfMemory가 발생하는거지?
7. 소프트웨어 공학
- 소프트웨어를 구조적으로 잘 설계하고, 구현하기 위함
- 아키텍쳐, 클래스 다이어그램, 애자일
- 프로그램을 어떻게 설계할 수 있을까? 프로그램을 만드는 방식은 어떤것일까?
8. 선형대수학, 확률, 통계…
