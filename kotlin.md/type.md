## 15. 코틀린 타입 시스템
### 1. 널 가능성
1. 널 가능성(nullability)
    1. 정의 : NullPointerException 오류를 피할 수 있게 돕기 위한 코틀린 타입 시스템의 특성
2. 널이 될 수 있는 타입
    1. 정의 : 프로그램 안의 프로퍼티나 변수에 null을 허용하게 만드는 방법이다.
    2. 널이 될 수 있는 변수에 메서드를 호출하면 NullPointerException이 발생할 수 있으므로 안전하지 않아서 메서드 호출을 금지한다.
    3. 함수가 널을 인자로 받을 수 있게 하려면 타입 이름 뒤에 ?를 명시해야한다.
    4. 어떤 타입이든 타입 이름 뒤에 물음표를 붙이면 그 타입의 변수나 프로퍼티에 null 참조를 저장할 수 있다는 뜻이다.

    ```kotlin
    fun strLenSafe(s: String?) = ...
    ```

    5. 널이 될 수 있는 값을 널이 될 수 없는 타입의 변수에 대입할 수 없다.
    6. 널이 될 수 있는 타입의 값을 널이 될 수 없는 타입의 파라미터를 받는 함수에 전달할 수 없다.
    7. 널이 될 수 있는 타입의 값으로 할 수 있는 일
        1. null과 비교
        2. null과 비교하고 나면 컴파일러는 그 사실을 기억하고 null이 아님이 확실한 영역에서는 해당 값을 널이 될 수 없는 타입의 값처럼 사용할 수 있다.
3. 타입의 의미
    1. 타입은 분류로 타입은 어떤 값들이 가능한지와 그 타입에 대해 수행할 수 있는 연산의 종류를 결정한다.
4. 자바에서 NullPointerException 오류 다루는 방법
    1. 애노테이션을 사용해 값이 널이 될 수 있는지 여부를 표시 @Nullable,@NotNull하기도 한다.
