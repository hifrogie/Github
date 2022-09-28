## 1. 객체지향프로그래밍의 5가지 설계 원칙 SOLID
### 1. SOLID 원칙
1. SOLID원칙을 철저히 지키면 시간이 지나도 변경이 용이하고, 유지보수와 확장이 쉬운 소프트웨어를 개발하는 데 도움이 되는 것으로 알려져있다.

### 2. 단일 책임의 원칙 : SRP(Single Responsibility Principle)

```
//안 좋은예
class UserSettings {
  constructor(user) {
    this.user = user;
  }

  changeSettings(settings) {
    if (this.verifyCredentials()) {
      // ...
    }
  }

  verifyCredentials() {
    // ...
  }
}
```

```
//좋은 예
class UserAuth {
  constructor(user) {
    this.user = user;
  }

  verifyCredentials() {
    // ...
  }
}

class UserSettings {
  constructor(user) {
    this.user = user;
    this.auth = new UserAuth(user);
  }

  changeSettings(settings) {
    if (this.auth.verifyCredentials()) {
      // ...
    }
  }
}
```
- 위의 예제에서 UserSetting이라는 Class에서는 현재 2가지 기능을 하고 있다. 
- User의 인증과 그 인증이 유효하면 setting을 변경할 수 있는 기능들이 있다. 
- 위에서의 기능을 아래와 같이 분리를 한다면 Class는 각자 하나의 기능만 담당하며 수정에도 용이해진다.
1. 모든 클래스는 각각 하나의 기능만 가진다는 의미
2. 다시 말하면 해당 클래스가 제공하는 모든 서비스는 단 하나의 책임을 수행하는데 집중되어야한다는 원칙
3. SRP원칙을 적용하면 다른 클래스들이 서로 영향을 미치는 연쇄작용을 줄일 수 있습니다.
4. 응집도(cohesion)은 높이고 결합도(coupling)은 낮출 수 있죠.
    - 응집도
        - 응집도는 모듈에 포함된 내부 요소들이 연관돼 있는 정도를 나타낸다.
        - 모듈 내의 요소들이 하나의 목적을 위해 긴밀하게 협력한다면 그 모듈은 높은 응집도를 가진다.
        - 모듈 내의 요소들이 서로 다른 목적을 추구한다면 그 모듈은 낮은 응집도를 가진다.
        - 객체지향 관점에서 응집도는 객체 또는 클래스에 얼마나 관련 높은 책임들을 할당했는지를 나타낸다.
    - 결합도
        - 결합도는 의존성의 정도를 나타내며 다른 모듈에 대해 얼마나 많은 지식을 갖고 있는지를 나타낸다.
        - 어떤 모듈이 다른 모듈에 대해 자세한 부분까지 알고 있다면 두 모듈은 높은 결합도를 가진다.
        - 어떤 모듈이 다른 모듈에 대해 꼭 필요한 지식만 알고 있다면 두 모듈은 낮은 결합도를 가진다.
        - 결합도는 협력에 필요한 적절한 수준의 관계만을 유지하는 것이 중요하다.
        - 결합도는 한 모듈이 변경되기 위해서 다른 모듈의 변경을 요구하는 정도로 측정할 수 있다.
        - 내부 구현을 변경했을 때 이것이 다른 모듈에 영향을 미치는 경우 → 높은 결합도
        - 퍼블릭 인터페이스를 수정했을 때만 다른 모듈에 영향을 미치는 경우 → 낮은 결합도
        - 따라서 구현이 아닌 인터페이스에 의존하도록 코드를 작성해야 낮은 결합도를 얻을 수 있다.
5. 뿐만 아니라 책임을 적절하게 분배함으로써 코드의 가독성 향상, 유지보수 용이라는 이점까지 누릴 수 있으며 다른 원칙들을 적용하는 기초가 됩니다.
6. 사뭇 단순한 원칙이라고 생각될 수 있으나, 막상 실무에 적용하려 하면 프로젝트의 복잡하고 빈번하게 변하는 성격 때문에 적용하기가 쉽지 않습니다.

### 3. 개방 폐쇄 원칙 OCP(Open Close Principle)

```
//잘못된 예제
class MobilePhone {
    lateinit var brandName: String
}

class MobilePhoneUser {
    fun runMobileDevice(mobileServices: Any, mobilePhone: MobilePhone) {
        if (mobileServices is HuaweiMobileServices) {
            println("This device is running with Huawei Mobile Services")
        }
    }
}

class HuaweiMobileServices {
    fun addMobileServiceToPhone(mobilePhone: MobilePhone) { 
    	println("Huawei Mobile Services") 
    }
}
```

```
//올바른 예제
class MobilePhone {
    lateinit var brandName: String
}

class MobilePhoneUser {
    fun runMobileDevice(mobileServices: IMobileServices, mobilePhone: MobilePhone) {
        mobileServices.addMobileServiceToPhone(mobilePhone)
    }
}

interface IMobileServices {
    fun addMobileServiceToPhone(mobilePhone: MobilePhone)
}

class HuaweiMobileServices: IMobileServices {
    override fun addMobileServiceToPhone(mobilePhone: MobilePhone) { 
    	mobilePhone.brandName = "Huawei"
    	println("Huawei Mobile Services")
    }
}

class GoogleMobileServices: IMobileServices {
    override fun addMobileServiceToPhone(mobilePhone: MobilePhone) { 
    	mobilePhone.brandName = "Google"
    	println("Google Mobile Services") 
    }
}
```

- 늦은 초기화를 하려면 lateinit을 사용
- lateinit은 전역변수로 선언 후 null값ㅇ르 지정하지 않고 초기화 하는 방법이 있습니다. 
- 위의 코드를 보면 우리는 스마트폰 서비스 타입을 if-else 문으로 체크하고 있습니다.
- 이 경우는 좋지 못한 사례입니다. 왜냐면 새로운 스마트폰 서비스 타입이 나오면, 그 때마다 하나하나 if-else 문을 통해 추가해야하기 때문입니다. 잊고 추가하지 않을 수도 있고, 코드량도 정량적으로 늘게 됩니다.
- 우리는 모든 스마트폰 서비스를 위한 하나의 인터페이스를 가지는 것을 생각해볼 수 있습니다. 그리고 각각의 스마트폰 서비스 타입은 인터페이스를 구현하고, 고유한 특성을 가지고 있게 만들 수 있습니다. 그러므로 우리는 if-else 문을 통해 스마트폰 서비스 타입을 체크할 필요가 없습니다.

1. 소프트웨어의 모든 구성요소(클래스, 모듈, 함수)는 확장에는 열려있고, 변경에는 닫혀있어야한다.
2. 다시말하면 요구사항의 변경이나 추가사항의 발생하더라도, 기존 구성요소는 수정이 일어나지 말아야하며 쉽게 확장이 가능하여 재사용할 수 있어야 한다.
3. 로버트 마틴은 OCP는 관리가 용이하고 재사용 가능한 코드를 만드는 기반이며, OCP를 가능케 하는 중요한 메커니즘은 추상화와 다형성이라고 설명합니다.
    - 추상화 : 공통의 속성이나 기능을 묶어 이름을 붙이는 것
    - 다형성 : 부모클래스에서 물려받은 가상 함수를 자식클래스 내에서 오버라이딩 되어 사용되는 것
4. OCP는 객체지향의 장점을 극대화하는 아주 중요한 원리입니다.
    - 객체지향의 장점
        1. 소프트웨어의 생산성 향상
            1. 신뢰성 있는 소프트웨어를 쉽게 작성할 수 있다.(개발자가 만든 데이터를 사용하기 때문에 신뢰할 수 있다.)
            2. 코드를 재사용하기 쉽다 (상속, 캡슐화, 다형성으로 인해 재사용할 수 있다.)
            3. 업그레이드가 쉽다.
            4. 디버깅이 쉽다.
        2. 실세계에 대한 쉬운 모델링
            1. 실세계에 대한 모델링을 좀 더 쉽게 해준다. (모든 것을 객체들의 상호작용으로 생각)
        3. 보안성 향상
            1. 캡슐화, 데이터 은닉, 다형성으로 인해 필요한 정보를 재정의하거나 getter, setter를 이용하기 때문에 보안성이 높다.

5. 클래스를 설계할 때 변할 부분과 변하지 않을 부분을 명확히 구분해야겠습니다.
6. 변할 수 있는 부분은 추상화하여 상속하는 클래스가 의존할 수 있게 코드를 작성합니다.
7. 적당한 추상화 레벨을 선택해야 합니다.
8. 그래디 부치에 의하면 추상화란 다른 모든 종류의 객체로부터 식별될 수 있는 객체의 본질적인 특징이라고 정의합니다.
9. 이 본질적인 특징을 명확히 정의할 수 있어야겠습니다.
10. Interface란 이런 변하지 않을 본질적인 특징에 관한(추상화) 약속입니다. 
11. Interface의 내부 내용을 모르더라도 interface를 구현해 사용할 수있습니다.

### 4. 리스코브 치환의 원칙 : LSP(the Liskov Substitution Principle)

```
//잘못된 예제
abstract class Vehicle {
    protected var isEngineWorking = false
    abstract fun startEngine()
    abstract fun stopEngine()
    abstract fun moveForward()
    abstract fun moveBack()
}

class Car: Vehicle() {
    override fun startEngine() {
        println("Engine started")
        isEngineWorking = true
    }

    override fun stopEngine() {
        println("Engine stopped")
        isEngineWorking = false
    }

    override fun moveForward() {
        println("Moving forward")
    }

    override fun moveBack() {
        println("Moving back")
    }
}

class Bicycle: Vehicle() {
    override fun startEngine() {
        // 필요없는 메서드
    }

    override fun stopEngine() {
        // 필요없는 메서드
    }

    override fun moveForward() {
        println("Moving forward")
    }

    override fun moveBack() {
        println("Moving back")
    }
}
```

```
//올바른 예제
interface Vehicle {
    fun moveForward()
    fun moveBack()
}

abstract class VehicleWithEngine: Vehicle {
    
    private var isEngineWorking = false
    
    open fun startEngine() { 
    	isEngineWorking = true 
    }
    
    open fun stopEngine() {
    	isEngineWorking = false 
    }
}

class Car: VehicleWithEngine() {

    override fun startEngine() {
        super.startEngine()
        println("Engine started")
    }

    override fun stopEngine() {
        super.stopEngine()
        println("Engine stopped")
    }

    override fun moveForward() {
        println("Moving forward")
    }

    override fun moveBack() {
        println("Moving back")
    }
}

class Bicycle: Vehicle {

    override fun moveForward() {
        println("Moving forward")
    }

    override fun moveBack() {
        println("Moving back")
    }
}
```
- Vehicle 추상 클래스가 있다고 가정해봅시다. 해당 추상 클래스는 엔진 상태에 대한 정보와 앞/뒤 이동 메서드를 가지고 있습니다.
- 만약 우리가 자식 클래스로 자동차, 트럭, 택시 등 만들때, Vehicle  추상 클래스만 확장하면 될 것 같이 보입니다.
- 그러나 위의 코드는 보다시피 만약 우리가 Bicycle 클래스를 자식 클래스로 만들 때, Bicycle 은 엔진이 없기 때문에, startEngine, stopEngine 메서드는 필요 없어집니다. (성급한 추상화의 결과입니다)
- 이런 상황을 고치기 위해서는 Vehicle 을 상속받는 새로운 자식 클래스를 만들어 해결할 수 있습니다. 
- 그리고 새롭게 추가하는 클래스는 엔진을 가지고 있는 Vehicle 들에 대한 클래스로 정의 될 것 입니다.

1. 부모 클래스를 가리키는 포인터에 해당 클래스를 상속하는 자식 클래스를 할당하더라도 모든 기능이 정상적으로 작동해야 하며 자식 클래스의 상세 내부를 부모 클래스는 알 필요가 없다는 뜻입니다.
    - 포인터 : 다른 변수의 주소를 가지고 있는 변수
2. 서브 클래스가 확장에 대한 인터페이스를 준수해야 함을 의미
3. 한마디로 부모 클래스를 상속한 자식 클래스는 부모 클래스의 역할을 정확히 해야한다.
4. 보통 부모 클래스의 메소드를 override하면서 문제가 발생한다.
5. 부모 클래스의 기존 메소드를 자식 클래스가 수정하면서 문제가 생기는 것이다.
6. LSP를 지키는 가장 간단한 방법은 상속은 하되 override를 안하는 것
7. 상속을 할 때 override가 필요하다면 기존 부모 클래스의 메소드가 하던 역할을 충실히 수행하고 기능의 추가만 신중하게 수행하면 됩니다.
8. LSP는 결국 상속의 과정 중 메소드의 재정의가 필요하다면 현재 자식 클래스가 부모 클래스의 기존 메소드의 의미를 해치지는 않는지 신중히 고민하고 올바르게 상속하라는 의미라고 생각합니다.

### 5. 인터페이스 분리의 원칙 : ISP(Interface Segregation Principle)

```
//잘못된 예제
interface Animal {
    fun eat()
    fun sleep()
    fun fly() // 사실 글을 읽으시는 모두가 보자마자 엥? 여기에 이게 왜 나올까 생각할 수 있을 것 같다 정말 예시용 인 것 같다.
}

class Cat: Animal {
    override fun eat() {
        println("Cat is eating fish")
    }

    override fun sleep() {
        println("Cat is sleeping on its owner's bed")
    }

    override fun fly() {
        TODO("Not yet implemented") // Cats can't fly
    }
}

class Bird: Animal {
    override fun eat() {
        println("Bird is eating forage")
    }

    override fun sleep() {
        println("Bird is sleeping in the nest")
    }

    override fun fly() {
        println("Bird is flying so high")
    }
}
```

```
//올바른 예제
interface Animal {
    fun eat()
    fun sleep()
}

interface FlyingAnimal {
    fun fly()
}

class Cat: Animal {
    override fun eat() {
        println("Cat is eating fish")
    }

    override fun sleep() {
        println("Cat is sleeping on its owner's bed")
    }
}

class Bird: Animal, FlyingAnimal {
    override fun eat() {
        println("Bird is eating forage")
    }

    override fun sleep() {
        println("Bird is sleeping in the nest")
    }

    override fun fly() {
        println("Bird is flying so high")
    }
}
```

- 우리가 Animal 인터페이스를 구현했다고 가정하자. 그리고 인터페이스는 동물이 할 수 있는 행동들에 대한 메서드를 가지고 있을 것이다.
- 알다시피 Cat 은 날 수 없다. Cat 가 같은 클래스가 더 추가된다면, 이 역시도 모두 Fly 메서드는 불필요하다.
- 이런 이슈를 수정하기 위해서는 FlyingAnimal 같이 새로운 인터페이스를 추가하면 된다. Animal 클래스에서 fly 메서드를 제거하고, 새로운 인터페이스를 아래와 같이 추가시켰다.
- 그리고 필요에 따라 FlyingAnimal 인터페이스가 Animal 인터페이스를 확장하여, eat, sleep 에 대한 오버라이딩을 진행하지 않을 수도 있습니다.

1. 자신이 사용하지 않는 인터페이스는 구현하지 말아야한다는 원칙
2. 다시말하면, 하나의 큰 인터페이스를 상속 받기 보다는 인터페이스를 구체적이고 작은 단위들로 분리시켜 꼭 필요한 인터페이스만 상속하자는 의미
3. SRP가 클래스의 단일 책임을 강조했다면 ISP는 인터페이스의 단일책임을 강조합니다.
4. 인터페이스 하나의 크기가 크다는 것은 한 번에 지켜야될 약속이 많아진다는 것을 의미

### 6. 의존성 역전의 원칙 : DIP(Dependency Inversion Principle)

```
//잘못된 예제
class AndroidDeveloper {
    fun developMobileApp(){
        println("Developing Android Application by using Kotlin")
    }
}

class IOSDeveloper {
    fun developMobileApp(){
        println("Developing iOS Application by using Swift")
    }
}

fun main(){
    val androidDeveloper = AndroidDeveloper()
    val iOSDeveloper = IOSDeveloper()

    androidDeveloper.developMobileApp()
    iOSDeveloper.developMobileApp()
}
```

``` 
//올바른 예제
interface MobileDeveloper {
    fun developMobileApp()
}

class AndroidDeveloper(var mobileService: MobileServices): MobileDeveloper {
    override fun developMobileApp(){
        println("Developing Android Application by using Kotlin. " +
                "Application will work with ${mobileService.serviceName}")
    }
    enum class MobileServices(var serviceName: String) {
        HMS("Huawei Mobile Services"),
        GMS("Google Mobile Services"),
        BOTH("Huawei Mobile Services and Google Mobile Services")
    }
}

class IosDeveloper: MobileDeveloper {
    override fun developMobileApp() {
        println("Developing iOS Application by using Swift")
    }
}

fun main(){
    val developers = arrayListOf(
    	AndroidDeveloper(AndroidDeveloper.MobileServices.HMS),
        IosDeveloper(),
        AndroidDeveloper(AndroidDeveloper.MobileServices.GMS)
    )
    developers.forEach(MobileDeveloper::developMobileApp)
}
```

- 안드로이드, iOS 를 위한 어플리케이션을 만든다고 생각해봅시다. 
- 우리는 먼저 안드로이드 개발자와 iOS 개발자가 필요합니다.- 아래의 클래스들은 각각의 운영체제가 소유한 프로그래밍 언어를 사용하여 모바일 어플리케이션을 만들 때 필요한 메서드들을 가지고 있다고 가정합니다.
- 위의 코드에 대해서 어떤 문제가 있는지 글쓴이는 명시하지 않았다. 아마도 위의 코드 같은 방법으로 개발하게 되면, 세세한 구현은 다르겠지만 큰 범주에서 봤을 때, Android 했던 것을 iOS 에서도 다시 하는 경우가 생길 것이고, 이를 해결하기 위한 추상화를 진행하다보면 의존성을 가지는 클래스들이 생길 것이고 이때 외부에서 받아 해결하는 방식으로 진행해야한다.
-  위의 문제를 해결하기 위해서 우리는 MobileDeveloper 라는 인터페이스를 생성하자. 
- 그리고 이 클래스를 구현하는 AndroidDeveloper, IOSDeveloper 클래스를 생성하자. 
- 만약 우리가 각각 Developer 타입에 따라서 다른 데이터를 저장하기를 원한다면, 우리는 의존성 역전 원칙을 위해 멋지게 해결할 수 있다. 
- 또한 우리가 안드로이드에서도 더욱 세분화해서 스마트폰 타입에 따라 분리하는 것을 원한다고 가정하자.
- 결론적으로 Android, iOS 개발자가 같은 메서드를 통해 모바일 어플리케이션을 만들기 원하고 이때 Android 는 스마트폰 타입을 따로 받아서 처리하고싶다.

1. 상위 모듈은 하위 모듈에 의존해서는 안된다. 둘 다 추상화에 의존해야한다.
2. 추상화는 구체적인 것에 의존해서는 안된다. 구체적인 것은 추상화에 의존해야한다.
3. 클래스 사이에는 의존관계가 존재하기 마련이다.
4. 의존 관계가 존재하되, 구체적인 클래스에 의존하지 말고 최대한 추상화한 클래스에 의존하라는 뜻
5. 다시말하면 interface를 적극적으로 활용하라는 의미
6. 의존성 주입(Dependency Injection)
- DIP를 만족하면 의존성 주입이라는 기술로 변화를 쉽게 수용할 수 있는 코드를 작성할 수 있다.
- 의존성 주입이란 
     1. 구성요소간의 코드 내부가 아닌 외부에서 의존 객체를 생성하여 넘겨주는 디자인 패턴 중 하나이다.
```kotlin
        // 내부에서 멤버로 생성
class Person{
	private val dog = Dog() 
    
    	fun walk(){
    		dog.walk()
    	}
}

fun main(args: Array) { 
	val person = Person() 
    	person.walk() 
}
```
- Dog 클래스의 인스턴스를 Person 클래스 내부에서 생성해서 사용하게 된다.
- 이 때, Person클래스는 Dog 클래스에 의존성을 가지고 있다고 할 수 있는데 Dog클래스에 변화가 생기면 Dog 클래스를 참조하는 모든 클래스를 수정해줘야 한다.

```kotlin
// 외부에서 생성자로 주입
class Person(private val dog : Dog){
    	fun walk(){
    		dog.walk()
    	}
}

fun main(args: Array) { 
	val dog = Dog()
    	val person = Person(dog)
    	person.walk() 
}
```
    