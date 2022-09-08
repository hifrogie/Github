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