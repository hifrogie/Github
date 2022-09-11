## 4. while과 for 루프
### 1. while 루프

```
while (조건){
    //
}
do {
    //
} while(조건)
```

1. while 루프의 문법은 자바와 다르지 않다.
2. 조건이 참인 동안 본문을 반복 실행한다.

### 2. for 루프

```
fun fizzBuzz(i: Int) = when {
    i % 15 == 0 -> "FizzBuzz"
    i % 3 == 0 -> "Fizz"
    i % 5 == 0 -> "Buzz"
    else -> "$i "
}
for (i in 1..100){
    print(fizzBuzz(i))
} // 1 2 Fizz 4 Buzz
```
1. for루프의 가장 흔한 용례인 초깃값, 증가 값, 최종 값을 사용한 루프를 대신하기 위해 코틀린에서는 범위(range)를 사용한다.
2. ex) val oneToTen = 1..10
3. 범위는 기본적으로 두 값으로 이뤄진 구간이다. 보통은 그 두 값은 정수 등의 숫자 타입이며 .. 연산자로 시작 값과 끝 값을 연결해서 범위를 만든다.
4. 코틀린의 범위는 닫힌 구간 또는 양 끝은 포함하는 구간이다. 이는 두 번째 값(위 예에선 10)이 항상 범위에 포함된다.
5. 이터레이션 : 소스 코드내에서 특정한 부분의 코드가 반복적으로 수행될 수 있도록 하는 구문
6. 이런 식으로 어떤 범위에 속한 값을 일정한 순서로 이터레이션하는 경우를 수열(progression)이라고 부른다.

### 3. Map에 대한 이터레이션

```
val binaryReps = TreeMap<Char, String>()

for (c in 'A'..'F'){
    val binary = Integer.toBinaryString(c.toInt())
    binaryReps[c] = binary
}

for((letter, binary) in binaryReps){
    println("$letter = $binary")
}
```

1. ..연산자를 문자 타입에도 적용할 수 있다. 'A'..'F'는 A부터 F에 이르는 문자를 모두 포함하는 범위를 만든다.
2. for 루프를 사용해 이터레이션하려는 컬렉션의 원소를 푸는 방법을 보여준다.
3. binaryReps[ c ] = binary 라는 코드는 binaryReps.put(c,binary)라는 자바 코드와 같다.
