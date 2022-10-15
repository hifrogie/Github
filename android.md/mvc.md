## 8. < Design Pattern> MVC,MVP,MVVM 비교
### 1. MVC
![이미지](https://velog.velcdn.com/images%2Fdin0121%2Fpost%2F0329d7ab-089a-4303-8795-d28763962c4b%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-12-17%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%207.21.34.png)
1. MVC 패턴은 Model+View+Controller를 합친 용어입니다.
2. 프로그램을 역할에 따라 Model,View,Controller로 나누어 설계한 아키텍쳐 패턴입니다.
3. 구조
    1. Model : 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분
    2. View : 사용자에게 보여지는 UI 부분
    3. Controller : 사용자의 입력(Action)을 받고 처리하는 부분입니다.
4. 동작
    1. 모든 입력(Input)들은 Controller로 전달됩니다.
    2. Controller는 입력에 해당하는 Model을 업데이트 합니다.
    3. 업데이트 결과에 따라 View를 선택합니다.
    4. 하나의 Controller는 View를 선택할 수 있기 때문에 여러개의 View를 관리할 수 있습니다.
    5. Controller는 View를 선택할 뿐, 직접 업데이트를 하지 않습니다.
    6. View를 업데이트하기 위한 방법
        - View가 Model을 이용하여 직접 업데이트 하는 방법
        - Model에서 View에게 Notify(알리다) 하여 업데이트 하는 방법
        - View가 Polling으로 주기적으로 Model의 변화를 감지하여 업데이트 하는 방법
            - Polling : 하나의 장치가 충돌 회피 또는 동기화 처리 등을 목적으로 다른 장치의 상태를 주기적으로 검사하여 일정한 조건을 만족할 때 송수신등의 자료처리를 하는 방식
            - 동기화 : 시스템을 동시에 작동시키기 위해 여러 사건들을 조화시키는 것을 의미
5. 장점
    1. 가장 단순한 패턴이기도하고 널리 사용되고 있는 패턴이다.
6. 단점
    1. View와 Model 사이의 의존성이 높다.
    2. 높은 의존성은 앱이 복잡해지고 유지보수가 어려워집니다.

### 2. MVP

![이미지](https://velog.velcdn.com/images%2Fdin0121%2Fpost%2Fb7988e2f-3609-4c4c-a4c4-3e5eacc6ed6a%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-12-17%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%207.40.54.png)

1. MVP 패턴은 Model+View+Presenter를 합친 용어입니다.
2. MVC에서 파생된, Model과 View간의 의존성이 없는 아키텍쳐 패턴입니다. 
3. 구조 
    1. Model : 앱에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
    2. View : 사용자에서 보여지는 UI부분입니다.
    3. Presenter : View에서 요청한 정보로 Model을 가공하여 View에 전달해 주는 부분입니다.
4. 동작
    1. 모든 입력(Input)들은 View로 전달됩니다.
    2. Presenter는 입력에 해당하는 Model을 업데이트 합니다.
    3. Model 업데이트 결과를 기반으로 View를 업데이트 합니다.
    4. Presenter는 해당 View를 참조하고 있습니다.(View와 Presenter는 1:1 관계입니다.)
    5. Presenter는 View와 Model 인스턴스를 가지고, Model과 View 사이의 매개체 역할을 합니다.
    - Presenter는 M-V 사이에서 관리를 해주기 때문에, MVC 패턴과 달리 M-V 사이의 의존성이 없습니다.
5. 장점
    1. MVP 패턴의 장점은 View와 Model의 의존성이 없다는 것
6. 단점
    1. MVP 패턴의 단점은 View와 Model 사이의 의존성은 해결되었지만, View와 Presenter 사이의 의존성이 커진다는 단점이 있다.
    2. 앱이 복잡해질수록 View와 Presenter 사이의 의존성이 강해지는 단점이 있습니다.

### 3. MVVM

![이미지](https://velog.velcdn.com/images%2Fdin0121%2Fpost%2Faf708306-e4d3-4055-b9e5-6871a5b27216%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-12-17%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%207.21.23.png)

1. MVVM 패턴은 Model+View+View Model을 합친 용어입니다.
2. MVC에서 파생된, Model과 View간의 의존성 뿐만 아니라 Controller과 View간의 의존성도 고려하여 각 구성 요소가 독립적으로 작성되고 테슽트 될 수 있도록 설계된 아키텍쳐 패턴 입니다.
3. 구조
    1. Model : 앱에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
    2. View : 사용자에서 보여지는 UI 부분입니다.
    3. View Model : View를 표현하기 위해 만든 View를 위한 Model입니다.
    4. View를 나타내주기 위한 Model이자 View를 나타내기 위한 데이터 처리를 하는 부분입니다.
4. 동작
    1. 모든 입력(Input)들은 View로 전달됩니다.
    2. ViewModel은 입력에 해당하는 Presentation Logic을 처리하여 View에 데이터를 전달합니다.
    3. ViewModel은 View를 참조하지 않기 때문에 독립적입니다.
    4. 따라서 View는 자신이 이용할 ViewModel을 선택해 바인딩하여 업데이트를 받게 됩니다.(Command 패턴이나 Data Binding을 이용하여 V-VM 간 의존성을 없앨 수 있습니다. 그리고 View Model과 View는 1:n 관계입니다.)
    5. Model이 변경되면 해당하는 ViewModel을 이용하는 View가 자동으로 업데이트 됩니다.
    6. ViewModel은 View를 나타내주기 위한 Model이자, View의 Presentation Logic을 처리합니다.
5. 장점
    1. View와 Model사이의 의존성이 없습니다.
    2. Command 패턴과 Data Binding을 사용하여 View와 ViewModel 사이의 의존성 또한 없앤 패턴입니다.
    3. 중복되는 코드를 모듈화하여 개발할 수 있습니다.
6. 단점
    1. ViewModel의 설계가 쉽지않다.

### 4. Clean Architecture
![이미지](https://blog.kakaocdn.net/dn/Tc5dZ/btqJV6DkmDt/igcmZnGORlSkuBjo9Uokqk/img.jpg)
1. Clean Architecture
    - 코드를 잘 분리하고, Testable한 구조를 가지고, 변경이 용이한 코드등의 목적을 만족하기 위해 만들어진 아키텍쳐들 중 장점들을 모아 정의한 것
    - 클린 아키텍쳐의 목적은 의존성 규칙을 통한 계층을 분리하는 것
2. 의존성 규칙
    1. 바깥쪽의 원은 메커니즘(Mechanism)이고 안쪽의 원은 정책(Policy)이다.
    2. 소스코드 의존성은 외부에서 내부로 향하는 고수준 정책에 따라야 한다.
    3. 원 안쪽으로 갈 수록 의존성이 낮아지게 된다.(안쪽의 원은 바깥쪽 원에 대해 전혀 알지 못한다.)
3. 계층에 대한 설명
    1. Entities
        1. 엔티티는 메서드를 갖는 객체, 데이터 구조, 함수의 집합들을 말한다.
        2. 가장 일반적이면서 고수준의 비지니스 규칙을 캡슐화하며, 바깥쪽에서 어떤것이 변경되더라도 여기선 변하지 않는다.
        3. 애플리케이션의 동작에 대한 변경이 엔티티 계층에 주어지면 안된다.
    2. UseCase
        1. 유스케이스는 엔티티로부터 데이터 흐름을 조합하는 역할을 한다.
        2. 애플리케이션의 고유 규칙을 캡슐화하며, 엔티티에는 영향을 주지 않고 DB,FrameWork 및 UI에 대한 변경으로 부터 떨어지게 된다.
    3. Interface Adapters(Presenters)
        1. 호환성 문제를 해결할 수 있도록 도와주는 어댑터들의 집합
        2. 유스케이스와 엔티티가 사용하기 쉬운 형식으로 DB 또는 웹 등 외부의 기능에 사용하기 쉬운 형식으로 변환해주는 역할을 한다.
        3. MVC 패턴의 요소들이 모두 인터페이스 어댑터에 속한다.
    4. Frameworks & Drivers
        1. 가장 바깥쪽에 위치해 있고, 데이터 베이스나 웹 프레임워크로 구성되어있다.
        2. 안쪽의 원과 통신할 연결 코드 이외에는 별다른 코드를 작성하지 않는다.
4. android에 적용
    1. UI를 독립적이게 만든다.
    2. DataBase를 분리시킨다.
    3. 외부적인 설정에 독립적인 구조로 프레임워크에 의존적이지 않게 코드를 만든다.
    4. Test가 가능한 코드를 만든다.