## 10. 데이터 클래스
### 1. toString()

```
class Client(val name: String, val postalCode: Int){
    override fun toString() = "Client(name=$name, postalCode = $postalCode)"
}
fun main(args: Array<String>){
    val client1 = Client("오현석",4122)
    println(client1) //Client(name=오현석, postalCode = 4122)
}
```

1. 자바처럼 코틀린의 모든 클래스도 인스턴스의 문자열 표현을 얻을 방법을 제공한다.
2. 주로 디버깅과 로깅 시 이 메서드를 사용한다.

### 2. equals()

```
val client1 = Client("오현석",4122)
val client2 = Client("오현석, 4122)
println(client1 == client2) // false
```
1. 위 예제에서는 두 객체가 동일하지 않다.
2. 이는 Client 클래스의 요구 사항을 만족시키고 싶다면 equals를 오버라이드할 필요가 있다는 뜻이다.
3. 동등성 연산에 ==를 사용함
    1. 동등성(equality): 원시타입의 경우 ==는 두 피연산자의 값이 같은지 비교한다.
    2. 참조 비교(reference comparision) : 참조 타입의 경우 ==는 두 피연산자의 주소가 같은지를 비교한다.
    3. 따라서 자바에서 두 객체의 동등성을 알려면 equals를 호출해야 한다.
    4. 자바에서 equals 대신 ==를 호출하면 문제가 될 수 있다는 사실도 잘 알려져 있다.
    5. 코틀린에서는 == 연산자가 두 객체를 비교하는 기본적인 방법이다.
    6. ==는 내부적으로 equals를 호출해서 객체를 비교한다.
    7. 따라서 클래스가 equals를 오버라이드하면 ==를 통해 안전하게 그 클래스의 인스턴스를 비교할 수 있다.
    8. 참조 비교를 위해서는 ===연산자를 사용할 수 있다.

```
class Client(val name: String, val postalCode: Int){
    override fun equals(other: Any?): Boolean{
        if(other == null || other !is Client)
            return false
        return name == other.name && 
            postalCode == other.postalCode
    }
    override fun toString() = "Client(name=$name, postalCode=$postalCode)"
}
```

4. 코틀린에서는 override 변경자가 필수여서 실수로 override fun equals(other: Any?) 대신 override fun equals(other: Client)를 작성할 수는 없다.
5. 그래서 equals를 오버라이드하고 나면 프로퍼티의 값이 모두 같은 두 고객 객체는 동등하리라 예상할 수 있다.
6. 실제로 client1 == client2는 이제 true를 반환한다.
7. Client클래스로 복잡한 작업을 수행해보면 제대로 작동하지 않는 경우가 있다.
8. hashCode가 없다는 점이 원인이다.

### 3. hashCode()

```
class Clent(val name: String, val postalCode: Int){
    ...
    override fun hashCode():Int = name.hashCode()*31 + postalCode
}
```

1. 자바에서는 equals를 오버라이드할 때 반드시 hashCode도 함께 오버라이드해야 한다.
2. JVM언어에서는 hashCode가 지켜야 하는 "equals()가 true를 반환하는 두 객체는 반드시 같은 hashCode()를 반환해야한다."라는 제약이 있다.

### 4. 데이터 클래스

```
data class Client(val name: String, val postalCode: Int)
```

1. data라는 변경자를 클래스 앞에 붙이면 필요한 메서드를 컴파일러가 자동으로 만들어준다.
2. data 변경자가 붙은 클래스를 데이터 클래스라고 부른다.
3. Client 클래스는 자바에서 요구하는 모든 메서드를 포함한다.
    1. 인스턴스 간 비교를 위한 equals
    2. HashMap과 같은 해시 기반 컨테이너에서 키로 사용할 수 있는 hashCode
    3. 클래스의 각 필드를 선언 순서대로 표시하는 문자열 표현을 만들어 주는 toString
    
### 5. copy()
1. copy()는 왜 사용되나요?
    1. copy() : 객체를 복사하면서 일부 프로퍼티를 바꿀 수 있게 해준다.
    2. 왜 사용하나? 
        1. 객체를 메모리상에서 직접 바꾸는 대신 복사본을 만드는 편이 더 낫다.
        2. 복사본은 원본과 다른 생명주기를 가지며, 복사를 하면서 일부 프로퍼티 값을 바꾸거나 복사본을 제거해도 프로그램에서 원본을 참조하는 다른 부분에 전혀 영향을 끼치지 않는다.

```
class Client(val name: String, val postalCode: Int){
fun copy(name: String = this.name, postalCode:Int = this.postalCode) = Client(name,postalCode)
}

fun main(args: Array<String>){
    val lee = Client("개구리",4122)
    println(lee.copy(postalCode = 4000)) // Client(name=개구리,postalCode=4000)
}
```

### 6. data 클래스

```
data class User(val age: Int, val name: String)

fun main() {
    val a = User(20, "tom")
    val b = User(20, "tom")
    println("a == b: ${a == b} a.hashCode(): ${a.hashCode()}, b.hashCode(): ${b.hashCode()}")
}

a == b: true a.hashCode(): 115646, b.hashCode(): 115646
```

```
open class SuperUser(var gender: Int = 0)
data class User(val age: Int, val name: String) : SuperUser(0)

fun main() {
    val a = User(20, "tom")
    val b = User(20, "tom").apply {
        gender = 1
    }
    println("a == b: ${a == b} a.hashCode(): ${a.hashCode()}, b.hashCode(): ${b.hashCode()}")
}

//a == b: true a.hashCode(): 115646, b.hashCode(): 115646
```

```
abstract class SuperUser { abstract var gender: Int }
data class User(val age: Int, val name: String, override var gender: Int) : SuperUser()
```

1. data class로 클래스를 만들면 객체 간의 동등성 비교시 사용되는 hashCode 함수를 자동으로 만들어주기 때문에 단순히 데이터를 관리하는 것 뿐만 아니라 데이터 간의 비교도 쉬워진다.
2. 첫번째 코드의 User 데이터 클래스로 선언된 a,b변수는 모두 다른 메모리에서 선언됐지만 hashCode 상으로는 동일한 값을 보이므로 동등성 비교에서는 같은 값을 보인다.
3. data class에서 상속을 사용하는 경우 주의가 필요하다.
4. 값을 변경했어도 data class 내부 멤버 변수가 아니라 부모 클래스의 변수를 변경했을 때는 hashCode 값이 변경되지 않는다.
5. 이는 data class가 자동으로 생성한 hashCode 함수가 부모 클래스의 변수를 포함하지 않아서 발생하는 문제다.
6. 그래서 가능하면 상속을 쓰지 않는 것이 좋다.
7. 꼭 써야한다면 data class가 자동 생성하는 hashCode가 동작할 수 있도록 추상 클래스나 인터페이스를 활용하는 것이 좋다.

### 7. data 클래스의 equals, hashCode의 동작
1. equals()
    1. 상속받은 equals 기본 동작은 객체의 주소 값의 비교이다.
    2. 이것은 코틀린의 ==이 수행되었을 때 동작과 일치한다.
    3. ==는 기본적으로 객체의 주소 값을 비교하여 일치값을 판단한다.
    4. 코틀린에서 객체의 값을 비교하고 싶을 때는 equals를 override 할 수 밖에 없다.

     ```kotlin
     class Client(val name: String,val postalCode: Int){
         override fun equals(other: Any?) : Boolean{
             if(other == null || other !is Client) return false
             return name == other.name && postalCode == other.postalCode
         }
     }
     ```
2. hashCode()
    1. equals()메서드와 함께 hashCode()메서드도 같이 오버라이드해야한다.
    2. JVM 언어에는 equals()가 true를 반환하는 두 객체는 반드시 같은 hashCode()를 반환해야한다.

     ```kotlin
     class Client(val name: String, val postalCode: Int){
         override fun equals(other: Any?) : Boolean {
             if(other == null || other !is Client) return false
             return name == other.name && postalCode == other.postalCode
         }
         override fun hashCode(): Int = name.hashCode() * 31 + postalCode
     }
     ```

