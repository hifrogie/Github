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

``` 
class Person(
    val name: String,
    var isMarried: Boolean
)