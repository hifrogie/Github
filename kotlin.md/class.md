## 2. 클래스와 프로퍼티
### 1. 클래스
1. 자바로 클래스 선언

```
public class Person{
    private final String name;

    public Person(String name){
        this.name = name;
    }
    public String getName(){
        return name;
    }
}
```

2. 같은 클래스를 코틀린으로 선언

```
class Person(val name: String)
```

- 이렇게 코드가 없이 데이터만 저장하는 클래스를 값 객체 (value object)라 부름
- public 가시성 변경자(visibility modifier)가 사라졌음, 코틀린의 기본 가시성은 public이므로 이런 경우 변경자를 생략해도 된다.

### 2. 프로퍼티
1. 자바에서는 필드와 접근자를 한데 묶어 프로퍼티(property)라고 부른다.
2. 코틀린은 프로퍼티를 언어 기본 기능으로 제공하며 코틀린 프로퍼티는 자바의 필드와 접근자 메서드를 완전히 대신한다.
3. var과 val로 선언하는 변수들이 프로퍼티

``` 
class Person(
    val name: String,
    var isMarried: Boolean
)
```

### 3. 프로퍼티와 변수의 차이
1. 코틀린에서 변수를 선언하면 내장된 getter와 setter함수가 자동으로 생성됨 그래서 일반적인 변수와는 달리 프로퍼티라는 명칭을 사용함

```
var name: String = "haruple"
val age: Int = 26
```

```
var name: String = "haruple"
    get() = field
    set(value) {field = value}
   
val age: Int = 26
    get() = field
```
2. 위 아래 코드는 완전히 같은 코드이다.
3. get,set함수를 자동으로 생성해주니 개발자가 따로 관리할 필요없이 일반적인 변수를 사용하듯 사용하면 된다.