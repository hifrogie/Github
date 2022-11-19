### 16. 연산자 오버로딩과 기타 관례
### 1. 산술 연산자 오버로딩
1. 이항 산술 연산 오버로딩

    ```kotlin
    data class Point(val x: Int, val y: Int){
     operator fun plus(other: Point): Point {
        return Point(x + other.x ,y + other.y)
        }
    }

    fun main(args: Array<String>){
        val p1 = Point(10, 20)
        val p2 = Point(30, 40)
        println(p1 + p2) // Point(x=40, y=60)
    }
    ```

    1. +로 계산하면 "plus" 함수가 호출된다.
    2. 연산자를 오버로딩하는 함수 앞에는 꼭 operator가 있어야 한다.
    3. operator 키워드를 붙임으로써 어떤 함수가 관례를 따르는 함수임을 명확히 할 수 있다.
    4. 코틀린에서는 프로그래머가 직접 연산자를 만들어 사용할 수 없고 언어에서 미리 정해둔 연산자만 오버로딩할 수 있으며, 관례에 따르기 위해 클래스에서 정의해야 하는 이름이 연산자별로 정해져있다.
    5. 우선순위는 연산자 우선순위와 같다.
    6. operator 함수도 오버로딩 가능

    |식|함수 이름|
    |:-:|:-:|
    |a*b|times|
    |a/b|div|
    |a%b|rem|
    |a+b|plus|
    |a-b|minus|

2. 복합 대입 연산자 오버로딩
    1. +=, -= 등의 연산자는 복합 대입 연산자(compound assignment)라 불린다.
    2. 변수가 변경 가능한 경우에만 복합 대입 연산자를 사용할 수 있다.
3. 단항 연산자 오버로딩
    
    |식|함수 이름|
    |:-:|:-:|
    |+a|unaryPlus|
    |-a|unaryMinus|
    |!a|not|
    |++a, a++|inc|
    |--a, a--|dec|

    1. 단항 연산자를 오버로딩하기 위해 사용하는 함수는 인자를 취하지 않는다.

### 2. 비교 연산자 오버로딩
1. 동등성 연산자: equals
    1. == 연산자 호출을 equals 메서드 호출로 컴파일한다.
    2. ===(식별자 비교 연산자 identity equals)를 사용해 equals의 파라미터가 수신 객체와 같은지 살펴본다.
2. 순서 연산자 : compareTo
    1. 비교 연산자(<,>,=<,>=)는 compareTo 호출로 컴파일 된다.
    2. compareTo가 반환하는 값은 Int다.
    3. p1 < p2는 p1.compareTo(p2) < 0 과 같다.

### 3. 컬렉션과 범위에 대해 쓸 수 있는 관례
1. 인덱스로 원소에 접근 : get과 set
    1. 코틀린에서는 인덱스 연산자도 관례를 따른다. 
    2. 인덱스 연산자를 사용해 원소를 읽는 연산은 get 연산자 메서드로 변환되고, 원소를 쓰는 연산은 set 연산자 메서드로 변환된다.
    3. x[a,b] 는 x.get(a,b)와 같다.
    4. x[a,b] = c는 x.set(a, b, c)

    ```kotlin
    data class MutablePoint(var x:Int, var y:Int)

    operator fun MutablePoint.set(index:Int, value: Int){
        when(index){
            0 -> x = value
            1 -> y = value
            else -> throw IndexOutOfBoundsException("Invalid coordinate $index")
        }
    }
    fun main(args: Array<String>){
        val p = MutablePoint(10, 20)
        p[1] = 42
        println(p) // MutablePoint(x=10, y=42)
    ```

2. in 관례
    1. in은 객체가 컬렉션에 들어있는지 검사(membership test)한다. 
    2. in 연산자와 대응하는 함수는 contains다.
3. rangeTo 관례
    1. 10..20로 닫힌 범위를 만들면 10이상 20이하인 범위가 생긴다.
    2. 10 until 20으로 만드는 열린 범위는 10 이상 19 이하인 범위가 생긴다.
    3. .. 연산자는 rangeTo 함수를 간략하게 표현하는 방법이다.
    4. start..end는 start.rangeTo(end)
4. for 루프를 위한 iterator 관례
    1. for(x in list){...}와 같은 문장은 list.iterator()를 호출해서 이터레이터를 얻은 다음 자바와 마찬가지로 그 이터레이터에 대해 hasNext와 next 호출을 반복하는 식으로 변환된다.
    
