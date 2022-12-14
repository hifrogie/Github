## 1. 스위프트 언어적 특성
### 1. 스위프트의 언어적 특성
1. 안정성(Safe)
    1. 옵셔널
    2. guard 구문
    3. 오류 처리
    4. 강력한 타입 통제
2. 신속성 (Fast)
    1. 스위프트는 C언어를 기반으로한 프로그래밍 언어를 대체하려는 목적으로 만들어졌습니다.
    2. 아직 미흡한 부분도 있지만 C언어의 수준과 동등한 성능을 일정한 수준으로 유지하는 데 초점을 맞춰 개발되었습니다.

### 2. 객체지향 프로그래밍 패러다임
1. 객체지향 프로그래밍은 컴퓨터 프로그램을 명령어의 목록으로 보는 기존의 프로그래밍 패러다임의 시각에서 벗어나 여러개의 독립된 단위인 객체의 모임으로 파악하고자하는 시각입니다. 
2. 각각의 객체는 서로 메시지를 주고 받고 데이터를 처리할 수 있습니다.
3. 프로그램을 유연하고 쉽게 변경할 수 있도록 작성할 수 있어 대규모 소프트 위어 개발에 많이 사용된다.
4. 소프트웨어의 질을 향상하려면 강한 응집력(Strong Cohesion)과 약한 결합력(Weak Coupling)을 지향해야한다.
5. 객체 지향 프로그램은 클래스에 하나의 문제해결을 위한 데이터와 메서드를 모아놓은 방식으로 응집력을 강화한다. 
6. 각 클래스는 독집적이 되도록 디자인해 결합력을 약화한다.

### 3. 함수형 프로그래밍 패러다임
1. 가장 큰 장점은 대규모 병렬처리가 쉽다.
2. 함수형 프로그래밍 패러다임은 프로그램이 상태의 변화 없이 데이터 처리를 수학적 함수 계산으로 취급하고자 하는 패러다임.
3. 함수형 프로그래밍은 순수하게 함수에 전달된 인자 값만 결과에 영향을 주므로 상태 값을 갖지 않고 순수하게 함수만으로 동작한다.
4. 따라서 어떤 상황에서 프로그램을 실행하더라도 일정하게 같은 결과를 도출할 수 있다.
5. 어떤 상황에서 프로그램을 실행하더라도 일정하게 같은 결과를 도출할 수 있다.
6. 프로그램이 동작하는 흐름에서 상태(값)가 변하지 않으면 함수 호출이 각각 상호 간섭없이 배타적으로 진행되므로 병렬처리할 때 부작용(side-effect)가 거의 없다.
7. 프로세스 혹은 스레드 별로 특정 값을 참조하기 위해 락을 걸거나 대기할 필요가 없기 때문이다.
8. 또한 필요한 만큼 함수를 나누어 처리할 수 있도록 스케일업 할 수 있기 때문에 대규모 병렬처리에 큰 강점이 있습니다.
9. 함수를 일급 객체(First-class Citizen)로 다룬다.
10. 다음 조건을 충족해야 일급객체가 될 수 있다.
    1. 전달인자로 전달할 수 있다.
    2. 동적 프로퍼티 할당이 가능하다.
    3. 변수나 데이터 구조 안에 담을 수 있다.
    4. 반환 값으로 사용할 수 있다.
    5. 할당할 때 사용된 이름과 관계없이 고유한 객체로 구별할 수 있다.