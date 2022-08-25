## 10. collection
### 1. collection
1. collection 이란?
    - 목록성 데이터를 처리하는 자료구조를 통칭한다.
    - 자료구조(Data Structure) : 여러 정보를 담는 것 
2. 자료 구조의 분류
    - List : 순서가 있는 목록
    - Set : 순서가 중요하지 않음
    - Queue : 먼저 들어온 것이 먼저 나감
    - Map : key-value로 저장됨

### 2. Collection 인터페이스
1. public interface Collection< E > extends Iterable< E >
    - Iterable< E >라는 인터페이스를 확장 했다.
    - Iterable 인터페이스에 선언되어 있는 메소드는 iterator() 하나다.

### 3. List 인터페이스
1. list는 List 인터페이스로부터 시작된다.
2. List 인터페이스는 Collection 인터페이스를 확장하였다.
3. Collection을 확장한 다른 인터페이스와 List 인터페이스의 가장 큰 차이점은 순서가 있다는 점이다.
4. List 인터페이스를 구현한 클래스들은 매우 많다. 그 중에서 java.util 패키지에서는 ArrayList, Vector, Stack, LinkedList를 많이 사용한다.
5. ArrayList와 Vector 클래스의 사용법은 거의 동일하고 기능도 거의 비슷하다. 이 두 클래스는 "확장 가능한 배열"이라고 생각하면 된다.
6. ArrayList는 Thread safe 하지 않고, Vector는 Thread safe하다.
7. Stack이라는 클래스는 Vector을 확장하여 만들었다.

### 4. ArrayList
1. ArrayList 클래스의 상속 관계
    - java.lang.Object
    - -> java.util.AbstractCollection< E >
    - -> java.util.AbstractList< E >
    - -> java.util.ArrayList< E >

2. ArrayList의 생성자

|생성자|설명|
|:--:|:--:|
|ArrayList()|객체를 저장할 공간이 10개인 ArrayList를 만든다.|
|ArrayList(Collection<? extends E> c)|매개 변수로 넘어온 컬렉션 객체가 저장되어 있는 ArrayList를 만든다.|
|ArrayList(int initialCapacity)|매개변수로 넘어온 initialCapacity 개수만큼의 저장공간을 갖는 ArrayList를 만듬|

3. ArrayList에 데이터를 담아보자
 - 하나의 데이터를 담을 때는 add()
 - Collection을 구현한 객체를 한꺼번에 담을 때는 addAll()

4. ArrayList에서 데이터를 꺼내자

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:------:|:----------------:|:-:|
|int|size()|ArrayList 객체에 들어가 있는 데이터의 개수를 리턴한다.|
|E|get(int index)|매개 변수에 지정한 위치에 있는 데이터를 리턴한다.|
|int|indexOf(Object o)|매개 변수로 넘어온 객체와 동일한 데이터의 위치를 리턴한다.|
|int|lastIndexOf(Object o)|매개 변수로 넘어온 객체와 동일한 마지막 데이터의 위치를 리턴한다.|

5. ArrayList에 있는 데이터를 삭제하자

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:------:|:----------------:|:-:|
|void|clear()|모든 데이터를 삭제한다.|
|E|remove(int index)|매개 변수에서 지정한 위치에 있는 데이터를 삭제하고, 삭제한 데이터를 리턴한다.|
|boolean|remove(Object o)|매개 변수에 넘어온 객체와 동일한 첫 번째 데이터를 삭제한다.|
|boolean|removeAll(Collection<?> c)|매개 변수로 넘어온 컬렉션 객체에 있는 데이터와 동일한 모든 데이터를 삭제한다.|

### 5. Stack 클래스
1. 마지막에 들어온 데이터를 가장 처음 꺼내는 LIFO 기능을 구현하려고 할 때 필요한 클래스다.
2. Stack 클래스의 상속관계
    - java.lang.Object
    - -> java.util.AbstractCollection< E >
    - -> java.util.AbstractList< E >
    - -> java.util.Vector< E >
    - -> java.util.Stack< E >

3. Stack클래스의 생성자는 Stack()이고 아무 데이터도 없는 Stack 객체를 만든다.

4. Stack 클래스의 메소드

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:------:|:----------------:|:-:|
|boolean|empty()|객체가 비어있는지를 확인한다.|
|E|peek()|객체의 가장 위에 있는 데이터를 리턴한다.|
|E|pop()|객체의 가장 위에 있는 데이터를 지우고, 리턴한다.|
|E|push(E item)|매개 변수로 넘어온 데이터를 가장 위에 저장한다.|
|int|search(Objec o)|매개 변수로 넘어온 데이터의 위치를 리턴한다.|