## 6. 함수를 호출하기 쉽게 만들기
### 1. toString 기본 구현

```
val list = listOf(1,2,3)
println(list) //[1,2,3]
```

1. 자바 컬렉션에는 디폴트 toString 구현이 들어있다. 
2. 하지만 그 디폴트 toString의 출력 형식은 고정돼 있고 우리에게 필요한 형식이 아닐 수도 있다.

### 2. 원하는 출력 형식으로 바꾸는 방법

```
fun <T> joinToString(
    collection: Collection<T>,
    separator: String,
    prefix: String,
    postfix: String
): String {
    val result = StringBuilder(prefix)

    for ((index, element) in collection.withIndex()){
        if(index > 0) result.append(separator)
        result.append(element)
    }
    result.append(postfix)
    return result.toString()
}
```

```
val list = listOf(1,2,3)
println(joinToString(list,"; ", "(",")"))   // (1; 2; 3)
```

1. 이 함수는 제네릭하다.
2. 즉, 이 함수는 어떤 타입의 값을 원소로 하는 컬렉션이든 처리할 수 있다.

### 3. 이름 붙인 인자

```
joinToString(collection, separator = " ",prefix = " ",postfix = "." )
```

1. 코틀린으로 작성한 함수를 호출할 때는 함수에 전달하는 인자 중 일부(또는 전부)의 이름을 명시할 수 있다. 
2. 호출 시 인자 중 어느 하라도 이름을 명시하고 나면 혼동을 막기 위해 그 뒤에 오는 모든 인자는 이름을 꼭 명시해야한다.

### 4. 디폴트 파라미터 값

```
fun <T> joinToString(
    collection: Collection<T>,
    separator: String = ", ",
    prefix: String ="",
    postfix: String =""
): String
```

```
joinToString(list, ",","","") //1, 2, 3

joinToString(list) // 1, 2, 3

joinToString(list, "; ") //1; 2; 3

joinToString(list, postfix = ";", prefix = "# ") // # 1, 2, 3;
```

1. 일반 호출 문법을 사용하려면 함수를 선언할 때와 같은 순서로 인자를 지정해야 한다.
2. 그런 경우 일부를 생략하면 뒷부분의 인자들이 생략된다.
3. 이름 붙인 인자를 사용하는 경우에는 인자 목록의 중간에 있는 인자를 생략하고, 지정하고 싶은 인자를 생략하고, 지정하고 싶은 인자를 이름 붙여서 순서와 관계없이 지정할 수 있다.
