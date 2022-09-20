## 11. 클래스 위임
### 1. 위임(Class Delegation)
1. 위임 : 하나의 클래스를 다른 클래스에 위임하도록 선언하여 위임된 클래스가 가지는 인터페이스 메소드를 참조없이 호출할 수 있도록 생성해주는 기능
2. 위임을 언어가 제공하는 일급 시민 기능으로 지원한다는 점이 코틀린의 장점이다.
    - 일급 시민 기능 : 함수를 일반 값처럼 다룰 수 있다.
### 2. by키워드
1. 인터페이스를 구현할 떄 by키워드를 통해 그 인터페이스에 대한 구현을 다른 객체에 위임 중이라는 사실을 명시할 수 있다.

    ```
    class CountingSet<T>(
    val innerSet: MutableCollection<T> = HashSet<T>()
) : MutableCollection<T> by innerSet {
    var objectsAdded = 0

    override fun add(element: T): Boolean {
        objectsAdded++
        return innerSet.add(element)
    }

    override fun addAll(c: Collection<T>): Boolean {
        objectsAdded += c.size
        return innerSet.addAll(c)
    }
}
    ```
