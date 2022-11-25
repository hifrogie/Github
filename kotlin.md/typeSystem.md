## 15. 코틀린 타입 시스템
### 1. 널가능성 Nullability
1. 널 가능성
    1. NullPointerException 오류를 피할 수 있게 돕기 위한 코틀린 타입 시스템의 특성
2. 널이 될 수 있는 타입
    1. 코틀린 시스템과 자바의 큰 차이는 '코틀린 타입 시스템이 널이 될 수 있는 타입을 명시적으로 지원한다.'는 점이다.
    2. 프로그램 안의 프로퍼티나 변수에 null을 허용하게 만드는 방법이다.
    3. 타입 이름 뒤에 ? 명시
    4. 널이 될 수 있는 타입인 변수에 대해 변수.메서드()처럼 직접 호출할 수는 없다.
    5. 널이 될 수 있는 값을 널이 될 수 없는 타입의 변수에 대입할 수 없다.
    6. 널이 될 수 있는 타입의 값을 널이 될 수 없는 타입의 파라미터를 받는 함수에 전달할 수 없다.
    7. 널과 비교하고 나면 컴파일러는 그 사실을 기억하고 null이 아님이 확실한 영역에서는 해당 값을 널이 될 수 없는 타입의 값처럼 사용가능
3. 타입의 의미
    1. 타입은 분류로 타입은 어떤 값들이 가능한지와 그 타입에 대해 수행할 수 있는 연산의 종류를 결정한다.
4. 자바에서 널 다루기
    1. 애노테이션으로 널이 될 수 있는지 여부를 표시 @Nullable, @NotNull 
5. 안전한 호출 연산자(?.)
    1. null 검사와 메서드 호출을 한 번의 연산으로 수행한다.
    2. 호출하려는 값이 null이 아니라면 ?.은 일반 메서드 호출처럼 작동한다. 호출하려는 값이 null이면 이 호출은 무시되고 null이 결과 값이 된다.
    3. 안전한 호출의 결과 타입도 널이 될 수 있는 타입
    4. 프로퍼티를 읽거나 쓸 때도 안전한 호출을 사용할 수 있다.
6. 엘비스 연산자(?:)
    1. null 대신 사용할 디폴트 값을 지정할 때 편리하게 사용할 수 있는 연산자를 제공한다.
    2. 이항 연산자로 좌항을 계산한 값이 널인지 검사한다. 좌항 값이 널이 아니면 좌항 값을 결과로 하고 좌항 값이 널이면 우항 값을 결과로 한다.
7. 안전한 캐스트(as?)
    1. 어떤 값을 지정한 타입으로 캐스트한다. as?는 값을 대상 타입으로 변환할 수 없으면 null을 반환한다.
8. 널 아님 단언(!!)
    1. 어떤 값이든 널이 될 수 없는 타입으로 강제로 바꿀 수 있다.
9. 나중에 초기화할 프로퍼티
    1. lateinit 변경자를 붙이면 프로퍼티를 나중에 초기화할 수 있다.
    2. var만 사용
10. 타입 파라미터의 널 가능성
    1. 코틀린에서는 함수나 클래스의 모든 타입 파라미터는 기본적으로 널이 될 수 있다.
    2. 타입 파라미터 T를 클래스나 함수 안에서 타입 이름으로 사용하면 이름 끝에 물음표가 없더라도 T가 널이 될 수 있는 타입이다.
11. 플랫폼 타입
    1. 코틀린이 널 관련 정보를 알 수 없는 타입을 말한다.

### 2. 코틀린의 원시 타입
1. 원시 타입
    1. 자바는 참조 타입이 필요한 경우 특별한 래퍼 타입(java.lang.Integer)으로 원시 타입 값을 감싸서 사용한다.
    2. 코틀린은 원시 타입과 래퍼 타입을 구분하지 않으므로 항상 같은 타입을 사용한다.
    3. 코틀린에서는 원시 타입의 값에 대해 메서드를 호출할 수 있다.
2. 숫자 변환
    1. 코틀린은 한 타입의 숫자를 다른 타입의 숫자로 자동 변환하지 않는다.
    2. 대신 직접 변환 메서드를 호출해야 한다.
    3. 코틀린은 모든 원시타입(boolean은 제외)에 대한 변환 함수를 제공한다.
    4. ex) toByte(), toShort(), toChar() 
    5. 숫자 리터럴을 사용할 때는 변환 함수를 호출할 필요가 없다.
    6. 42L이나 42.0f처럼 상수 뒤에 타입을 표현하는 문자를 붙이면 변환이 필요없다.
    7. 숫자 리터럴을 타입이 알려진 변수에 대입하거나 함수에게 인자로 넘기면 컴파일러가 필요한 변환을 자동으로 넣어준다.
3. Any, Any?:최상위 타입
    1. 코틀린에서는 Any타입이 원시타입을 포함한 모든 널이 될 수 없는 타입의 조상 타입이다.
    2. 원시 타입 값을 Any 타입의 변수에 대입하면 자동으로 값을 객체로 감싼다.

    ```kotlin
    val answer: Any = 42 // Any가 참조 타입이기 때문에 42가 박싱된다.
    ```

    3. 널을 포함하는 모든 값을 대입할 변수를 선언하려면 Any? 타입을 사용해야한다.
    4. 모든 코틀린 클래스에는 toString, equals, hashCode 라는 세 메소드가 들어있다. 이 세 메서드는 Any에 정의된 메서드를 상속한 것이다.
4. Unit 타입 : 코틀린의 void
    1. 내용을 전혀 반환하지 않는 함수의 반환 타입으로 Unit을 쓸 수 있다.
    2. 이는 반환 타입 선언 없이 정의한 블록이 본문인 함수와 같다.
    3. 코틀린의 Unit이 자바 void와 다른 점은 무엇일까?
        1. Unit은 모든 기능을 갖는 일반적인 타입
        2. void와 달리 Unit을 타입인자로 쓸 수 있다.
        3. Unit 타입에 속한 값은 단 하나뿐이며, 그 이름도 Unit이다.
        4. Unit 타입의 함수는 Unit 값을 묵시적으로 반환한다.
5. Nothing 타입 
    1. 코틀린에는 결코 성공적으로 값을 돌려주는 일이 없으므로 반환 값이라는 개념 자체가 의미 없는 함수가 일부 존재한다.
    2. 그런 함수를 호출하는 코드를 분석하는 경우 함수가 정상적으로 끝나지 않는 다는 사실을 알면 유용하다. 그런 경우를 표현하기 위해 코틀린에는 Nothing이라는 특별한 반환 타입이 있다.
    3. Nothing 타입은 아무 값도 포함하지 않는다. 따라서 Nothing은 함수의 반환 타입이나 반환 타입으로 쓰일 타입 파라미터로만 쓸 수 있다.
    4. 그 외의 다른 용도로 사용하는 경우 Nothing 타입의 변수를 선언하더라도 그 변수에 아무 값도 저장할 수 없으므로 아무 의미도 없다.

    ```kotlin
    val address = company.address ?: fail("No address")
    println(address.city)
    ```

    5. 이 예제는 Nothing이 얼마나 유용한지 보여준다.
    6. 컴파일러는 Nothing이 반환 타입인 함수가 결코 정상 종료 되지 않음을 알고 그 함수를 호출하는 코드를 분석할 때 사용한다.
    7. 컴파일러는 company.address가 널인 경우 엘비스 연산자의 우항에서 예외가 발생한다는 사실을 파악하고 address의 값이 널이 아님을 추론할 수 있다.

### 3. 컬렉션과 배열
1. List< Int?>  vs List< Int>?
    1. 첫 번째 경우 리스트 자체는 항상 널이 아니다. 하지만 리스트에 들어있는 각 원소는 널이 될 수도 있다.
    2. 두 번째 경우는 리스트를 가리키는 변수에는 널이 들어갈 수 있지만 리스트 안에는 널이 아닌 값만 들어간다.

