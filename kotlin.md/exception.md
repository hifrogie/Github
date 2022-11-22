## 5. 코틀린의 예외 처리
1. 코틀린의 예외 처리는 자바나 다른 언어의 예외 처리와 비슷하다. 
2. 함수는 정상적으로 종료할 수 있지만 오류가 발생하면 예외를 던질(throws)수 있다.
3. 함수를 호출하는 쪽에서 그 예외를 잡아 처리할 수 있다.
4. 발생한 예외를 함수 호출 단에서 처리하지 않으면 함수 호출 스택을 거슬러 올라가면서 예외를 처리하는 부분이 나올 때까지 예외를 다시 던진다(rethrow).

```
if(percentage !in 0..100){
    throw IllegalArgumentException(
        "A percentage value must be between 0 and 100: $percentage")
}
```

5. 자바와 달리 코틀린의 throw는 식이므로 다른 식에 포함될 수 있다.

```
val percentage = 
    if (number in 0..100)
    number
    else
    throw IllegalArgumentException(
        "A percentage value must be between 0 and 100 : $number"    )
```

6. 이 예제에서 if의 조건이 참이므로 프로그램이 정상 동작해서 percentage 변수가 number의 값으로 초기화된다. 하지만 조건이 거짓이면 변수가 초기화되지 않는다.
7. 자바와 마찬가지로 예외를 처리하려면 try와 catch,finally 절을 함께 사용한다.

```
fun readNumber(reader: BufferedReader): Int? {
    try{
        val line = reader.readLine()
        return Integer.parseInt(line)
    }
    catch (e: NumberFormatException){
        return null
    }
    finally{
        reader.close()
    }
}
val reader = BufferedReader(StringReader("239"))
println(readNumber (reader))
```

8. 자바 코드와 가장 큰 파이는 throw 절이 코드에 없다.
9. 자바에서는 함수를 작성할 때 함수 선언 뒤에 throw IOException을 붙여야 한다.
10. 이유는 IOException이 체크 예외(checked exception)이기 때문이다.
11. 자바에서는 체크 예외를 명시적으로 처리해야 한다. 
12. 어떤 함수가 던질 가능성이 있는 예외나 그 함수가 호출한 다른 함수에서 발생할 수 있는 예외를 모두 catch로 처리해야하며 처리하지 않은 예외는 throws 절에 명시해야 한다.