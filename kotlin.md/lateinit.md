## 13. lateinit 과 lazy의 차이
### 1. lateinit

```
fun main() {
    lateinit var text: String

    // 대충 중간에 뭔가 했음
    val result1 = 30

    text = "Result : $result1"
    println(text)

    // 대충 뭔가 또 했음
    val result2 = 50

    text = "Result : ${result1 + result2}"
    println(text)
}
```

1. lateinit 변수 선언부를 자세히보면 var로 선언되어있다.
2. Primitive Type에는 사용할 수 없다.

### 2. by lazy

```
fun main() {
    lateinit var text: String
    val textLength: Int by lazy {
        text.length
    }

    // 대충 중간에 뭔가 했음
    text = "H43RO_Velog"
    println(textLength)
}
```

1. by lazy 구문을 통해 어떤 생성자를 넣어준 모양이다.
2. 그런데 자세히 보면 lateinit 이라서 아직 초기화 되지 않은 text의 속성을 활용한 모습을 볼 수 있다.
3. by lazy는 선언 당시에는 초기화할 방도가 없지만 이후에는 의존하는 값들이 초기화된 이후에 값을 채워 넣고 싶을 때 사용한다.
4. 즉 호출시에 이를 어떻게 초기화를 해줄지에 대해서 정의할수 있는 구문이다.
5. 따라서 text가 초기화된 이후에 textLength를 출력할 때 text.length 속성을 사용하여 textLength라는 변수를 초기화 할 수 있다.
6. 선언부를 자세히 보면 val로 선언되어있는 것을 볼수 있다. 이는 단 한번의 늦은 초기화가 이루어지고 이후에는 값이 불편함을 보장한다.

### 3. 특징
1. 값 변경이 가능한가?
    - lateinit : 가능 (var 사용)
    - by lazy : 불가능 (val 사용)
2. 용법 구분
    - lateinit : 초기화 이후에 계속하여 값이 바뀔 수 있을 때
    - by lazy : 초기화 이후에 읽기 전용 값으로 사용할 때