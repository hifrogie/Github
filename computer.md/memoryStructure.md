## 3.Memory Structure
### 1. 프로그램 실행 순서

![실행순서](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcQRqku%2Fbtru0vJ6Ixx%2F9qCTW7ChXc80fGfQUrT4B0%2Fimg.png)

1. 자바로 개발된 프로그램을 실행하면 jvm은 os로부터 메모리를 할당받습니다.
2. 자바 컴파일러(javac)가 자바 소스코드를(.java) 지바 바이트코드(.class)로 컴파일합니다.
3. class loader를 통해 바이트 코드를 jvm runtime data area로 로딩합니다.
4. runtime data area에 로딩된 바이트 코드(.class)들은 execution engine을 통해 해석합니다.
5. 해석된 바이트 코드는 runtime data area의 각 영역에 배치되어 수행하며 이 과정에서 execution engine에 의해 gc의 작동과 스레드 동기화가 이루어집니다.

- 쓰레드 동기화 : 한 쓰레드가 진행 중인 작업을 다른 스레드가 간섭하지 못하도록 막는 것

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbZR97z%2FbtrvtdBl1Md%2FLbUk2NVlgDmsKMcBiQ9f4K%2Fimg.png)

### 2. Runtime Data Area
1. 큰 단위로 분류
    1. 모든 쓰레드가 공유해서 사용(GC의 대상)
        - 힙 영역
        - 메서드 영역
    2. 쓰레드 마다 하나씩 생성
        - 스택 영역
        - pc 레지스터
        - 네이티브 메서드 스택
2. 메서드 영역
    1. 클래스 멤버 변수의 이름, 데이터 타입, 접근 제어자 정보와 같은 각종 필드 정보들과 메서드 정보, 데이터 type 정보, constant pool, static 변수, final class 등이 생성되는 영역입니다.

3. 스택(Stack) 영역
    1. 프로그램이 자동으로 사용하는 임시 메모리 영역이다.
    2. 함수 호출 시 생성되는 지역 변수와 매개 변수가 저장되는 영역이고, 함수 호출이 완료되면 사라집니다.

4. 힙(Heap)영역
    1. 프로그래머가 할당/해제하는 메모리 공간이다.
    2. Java에서는 가비지 컬렉터가 자동으로 해제합니다.
    3. 이 공간에 메모리 할당하는 것을 동적 할당(Dynamic Memory Allocation)이라고도 부른다.
    4. 예를 들어 클래스, 클로저가 이 부분에 해당 된다.
    5. 런타임 시에 크기가 결정된다.

    ![HEAP](https://i.imgur.com/GImVa8L.png)

    6. 위의 HEAP과 STACK영역은 사실 같은 공간을 공유한다.
    7. HEAP이 메모리 위쪽 주소부터 할당되면 STACK은 아래쪽부터 할당되는 식이다.
    8. 그래서 각 영역이 상대 공간을 침범하는 일이 발생할 수 있는데 이를 HEAP OVERFLOW,STSCK OVERFLOW라고 칭합니다.
    9. Stack 영역이 크면  클수록 Heap영역이 작아지고, Heap 영역이 클수록 Stack 영역이 작아집니다.

5. PC 레지스터
    1. Thread가 생성될 때마다 생성되는 영역으로 프로그램 카운터, 즉 현재 스레드가 실행되는 부분의 주소와 명령을 저장하고 있는 영역입니다.

6. 네이티브 메서드 스택
    1. 자바 이외의 언어로 작성된 네이티브 코드를 실행할 때 사용되는 메모리 영역이다.
    
### 3. Java Primitive Type VS Reference Type
1. Primitive Type(기본형 타입)
    - 실제 값을 저장하고 메모리는 스택 메모리에 저장된다.

2. Reference Type(참조형 타입)
    - 값이 저장되어 있는 곳의 주소 값을 저장하고, 메모리는 힙 메모리에 저장된다.

### 4. Static area
1. JAVA 파일은 크게 필드, 생성자, 메소드로 구성된다. 
2. 그 중 필드 부분에서 선언된 변수(전역 변수)와 정적멤버변수(static이 붙은 자료형) Static 영역에 데이터를 저장한다.
3. Static 영역의 데이터는 프로그램 시작 부터 종료가 될 때 까지 메모리에 남아있게 된다.
4. 전역변수가 프로그램이 종료될때까지 어디서든 사용이 가능한 이유이기도 하다.
5. 따라서 전역변수를 무분별하게 많이 사용하다 보면 메모리가 부족할 우려가 있어 필요한 변수만 사용할 필요가 있다.

### 5. 클래스 로더 (Class Loader)
1. 자바는 동적으로 클래스를 읽어오므로, 프로그램이 실행 중인 런타임에서야 모든 코드가 자바 가상 머신과 연결됩니다. 이렇게 동적으로 클래스를 로딩해주는 역할을 하는 것이 클래스 로더이다.
2. 클래스 로더는 자바 바이트 코드를 묶어서 jvm이 운영체제로 부터 할당받은 메모리 영역인 Runtime Data Area로 적재합니다.

### 6. 가비지 컬렉터(Garbage Collector)
1. 더는 사용하지 않는 메모리를 자동으로 회수해줌 따라서 개발자가 직접 메모리를 관리하지 않아도 된다.