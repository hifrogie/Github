## 3. enum과 when
### 1. enum 
``` 
enum class Color(val r: Int, val g: Int, val b:Int){
    RED(255,0,0), ORANGE(255,165,0), YELLOW(255, 255, 0),
    GREEN(0, 255, 0),BLUE(0,0,255),INDIGO(75,0,130),
    VIOLET(238,130,238);

    fun rgb() = (r * 256 + g) * 256 + b
}
println(Color.BLUE.rgb())//255
```

1. 매개 변수 부분 : 상수의 프로퍼티를 정의한다.
2. 각 상수를  생성할 때 그에 대한 프로퍼티 값을 지정한다.
3. 상수 마지막에 세미콜론을 사용해야한다.
4. enum클래스 안에서 메서드를 정의한다.

### 2. when

```
fun getMnemonic(color: Color) = 
    when (color) {
        Color.RED -> "Richard"
        Color.ORANGE -> "Of"
        Color.YELLOW -> "York"
        Color.GREEN -> "Gave"
        Color.BLUE -> "Battle"
        Color.INDIGO -> "In"
        Color.VIOLET -> "Vain"
    }
println(getMnemonic(Color.BLUE))//Battle
```

1. 앞의 코드는 color로 전달된 값과 같은 분기를 찾는다. 
2. 자바와 달리 각 분기 끝에 break를 넣지 않아도 된다.
3. 한 분기 안에 여러 값을 매치 패턴으로 사용할 수도 있다. 그럴 경우 값 사이를 콤마로 분리한다.

### 3. when과 임의의 객체를 함께 사용
1. 분기 조건에 상수만을 사용할 수 있는 자바 switch와 달리 코틀린의 분기 조건은 임의의 객체를 허용한다.

```
fun mix(c1: Color, c2: Color) = 
    when(setOf(c1,c2)){
        setOf(RED, YELLOW) -> ORANGE
        setOf(YELLOW, BLUE) -> GREEN
        setOf(BLUE, VIOLET) -> INDIGO
        else -> throw Exception("Dirty color")
    }
    println(mix(BLUE, YELLOW)) //GREEN
```

2. 코틀린 표준 라이브러리에는 인자로 전달받은 여러 객체를 그 객체들을 포함하는 집합인 set 객체로 만드느 setOf라는 함수가 있다.
3. set은 원소의 순서는 중요하지 않다. 따라서 setOf(c1,c2)와 setOf(RED,YELLOW)가 같다는 말은 c1은 RED이고 c2가 YELLOW거나 c1이 YELLOW이고 c2가 RED라는 말이다.
4. when 식은 인자 값과 매치하는 조건 값을 찾을 때까지 각 분기를 검사한다.