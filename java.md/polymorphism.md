## 1. 다형성
### 1. 다형성(polymorphism)이란?
   1. 부모-자식 상속 관계에 있는 클래스에서 상위클래스가 동일한 메세지로 하위 클래스들을 서로 다르게 동작시키는 객체 지향 원리
   2. 부모 클래스가 자식 클래스의 동작 방식을 알수 없어도 오버라이딩을 통해 자식 클래스에 접근할 수 있다.
   3. 동적바인딩 덕분에 부모가 자식이 어떤 일을 하는 지 몰라도, 자식 멤버 함수를 호출시킬 수 있다.
        1. 동적 바인딩 : 실행 시간 (Runtime) 즉, 파일을 실행하는 시점에 성격이 결정된다. 실제 참조하는 객체의 메소드를 호출한다. 
### 2. 다형성의 장점
   1. 여러 객체를 하나의 타입으로 관리가 가능하기 때문에 코드 관리가 편리해 유지보수가 쉽다.
   2. 다형성을 활용하면 객체를 재사용하기 쉬워지기 때문에 코드 재사용성이 높아집니다.
   3. 클래스간의 의존성이 줄어들어 확장성이 높고 결합도가 낮아져 안전성이 높아집니다.
      - 결합도 : 하나의 클래스가 다른 클래스와 얼마나 많이 연결되어있는지를 나타내는 표현, 결합도가 높은 프로그램은 유지보수가 어렵다.
### 3. 다형성 필수 조건
   1. 클래스 상속이 이루어져야됨
   2. 오버라이딩 필수
   3. 부모 타입으로 자식 클래스를 업캐스팅하여 객체를 생성해야 합니다.
### 4. 다형성 구현 방법
   1. 상속 클래스 구현
   2. 메소드 오버라이딩
   3. 업캐스팅하여 객체 선언
   4. 부모 클래스 객체로 자식 메소드 호출