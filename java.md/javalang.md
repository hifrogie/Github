## 8.java.lang 패키지
### 1. 숫자를 처리하는 클래스들
1. 기본 자료형의 숫자를 객체로 처리할 필요가 있을 때 사용한다.
2. 기본 자료형으로 선언되어 있는 타입의 클래스들이 선언되어 있다.
- Byte
- Short
- Integer
- Long
- Float
- Double
- Character
- Boolean
3. Character와 Boolean을 제외한 숫자를 처리하는 클래스들을 Wrapper 클래스라고 불린다.
4. Number라는 abstract클래스를 확장한다.
5. 참조자료형이지만 기본 자료형처럼 사용할 수있다. 왜냐하면 자바 컴파일러에서 자동으로 형변환을 해주기 때문이다.
6. Character 클래스를 제외하고는 공통적인 parse타입이름(), valueOf()메소드를 제공한다. 
7. 문자열을 기본자료형으로 바꿔주는 메소드이다. parse타입이름()은 기본자료형을 리턴하고, valueOf()는 참조 자료형을 리턴한다.
8. 숫자를 처리하는 참조 자료형을 만든 이유
    1. 매개 변수를 참조 자료형으로만 받는 메소드를 처리하기 위해
    2. 제네릭과 같이 기본 자료형을 사용하지 않는 기능을 사용하기 위해
    3. 클래스에 선언된 상수 값을 사용하기 위해서
    4. 문자열을 숫자로, 숫자를 문자열로 쉽게 변환하고 2,8,10,16진수 변환을 쉽게 처리하기 위해서

### 2. 각종 정보를 확인하기 위한 System 클래스
1. System 클래스는 생성자가 없다.
2. 3개의 static 변수
    |선언 및 리턴 타입|변수명|설명|
    | :------------:|:----:|:---:|
    |static PrintStream | err | 에러 및 오류를 출력할 때 사용한다.|
    | static InputStream|  in |  입력값을 처리할 때 사용한다.|
    |static PrintStream |out | 출력값을 처리할 떄 사용한다.|
3. 시스템 속성(Property)값 관리
    |리턴 타입|메소드 이름 및 매개 변수|설명|
    |:------:|:--------------:|:---:|
    |static String|clearProperty(String key)| key에 지정된 시스템 속성을 제거한다.|
    |static Properties|getProperties()|현재 시스템 속성을 Properties 클래스 형태로 제공한다.|
    |static void|setProperties(Properties props)|Properties 타입으로 넘겨주는 매개변수에 있는 값들을 시스템 속성에 넣는다.| 
4. 시스템 환경(Environment)값 조회
    |리턴 타입|메소드 이름 및 매개 변수|설명|
    |:------:|:--------------:|:---:|
    |static Map<String,String>|getenv()|현재 시스템 환경에 대한 Map형태의 리턴값을 받는다.|
    |static String|getenv(String name)|지정한 name에 해당하는 값을 받는다.|

5. GC 수행
    |리턴 타입|메소드 이름 및 매개 변수|설명|
    |:------:|:--------------:|:---:|
    |static void|gc()|가비지 컬랙터를 실행한다.|
    |static void|runFinalization()|GC 처리를 기다리는 모든 객체에 대하여 finalize() 메소드를 실행한다.|

6. JVM 종료
    |리턴 타입|메소드 이름 및 매개 변수|설명|
    |:------:|:--------------:|:---:|
    |static void|exit(int status)|현재 수행중인 JVM을 멈춘다.|

7. 현재 시간 조회
    |리턴 타입|메소드 이름 및 매개 변수|설명|
    |:------:|:--------------:|:---:|
    |static long| currentTimeMillis()|현재 시간을 밀리초 단위로 리턴한다.|
    |static long| nanoTime()|현재 시간을 나노초 단위로 리턴한다.|