## 4. enum 클래스의 메모리 구조
### 1. enum과 메모리 구조
   1. 열거 상수는 상수 각각을 내부적으로 public static final 필드 이면서 객체로 제공되도록 합니다.
   2. static이 붙어있기 때문에 각각의 상수는 클래스 변수로 클래스 로더가 로드 시점에 JVM Method 영역에 해당 클래스 변수들을 항상 상주시켜 프로그램이 종료되기 전에는 언제든 가져다 쓸 수 있는 주소 공간을 확보합니다.
    ![메소드 영역 이미지](https://honbabzone.com/assets/images/post/java/emum-memory.png)
### 2. enum, 싱글톤 패턴의 공통점
   1. 생성자의 제한자가 private 이다.
   2. enum은 run-time이 아닌 compile-time에 모든 값을 알고 있어야함. 즉 다른 패키지나 클래스에서 enum 타입에 접근해서 동적으로 어떤 값을 정해줄 수 없다.
### 3. enum, 싱글톤 패턴의 차이점
   1. enum의 상수에 접근할 때는 enum클래스.상수
   2. 싱글톤의 객체를 생성하려면 정적 필드에 할당된 하나의 new 생성자를 호출하는 메소드를 호출하면 된다.