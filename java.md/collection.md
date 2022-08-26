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

### 6. Set
1. Set이 왜 필요하지?
 - 중복되는 것을 방지하고 순서에 상관없이 어떤 데이터가 존재하는지 확인하기 위한 용도로 사용

 2. Set 인터페이스를 구현한 주요 클래스
    - HashSet : 순서가 전혀 필요없는 데이터를 hash table에 저장한다, Set중에 가장 성능이 좋다.
    - TreeSet : 저장된 데이터의 값에 따라서 정렬되는 셋이다. red-black이라는 트리 타입으로 값이 저장되며 HashSet보다 성능이 느리다.
    - LinkedHashSet : 연결된 목록 타입으로 구현된 해시 테이블에 테이터를 저장한다. 저장된 순서에 따라서 값이 정렬된다. 성능은 제일 나쁘다.

### 7. HashSet
 1. HashSet 클래스의 상속 관계
  - java.lang.Object
  - -> java.util.AbstractCollection< E >
  - -> java.util.AbstractSet< E >
  - -> java.util.HashSet< E >

2. HashSet의 생성자

|생성자|설명|
|:---:|:-:|
|HashSet()|데이터를 저장할 수 있는 16개의 공간과 0.75의 load factor를 갖는 객체를 생성한다.|
|HashSet(Collection<? extends E> c)|매개 변수로 받은 컬랙션 객체의 데이터를 HashSet에 담는다.|
|HashSet(int initialCapacity)|매개 변수로 받은 개수만큼의 데이터 저장 공간과 0.75 load factor를 갖는 객체를 생성한다.|
|HashSet(int initialCapacity, float loadFactor)|첫 매개 변수로 받은 개수만큼의 데이터 저장 공간과 두 번째 매개 변수로 받은 만큼의 load factor를 갖는 객체를 생성한다.|

- load factor는 (데이터의 개수/저장 공간)을 의미한다.
- 데이터의 개수가 증가하여 로드 팩터 보다 커지면 저장공간의 크기는 증가되고 해시 재정리 작업을(rehash) 해야만 한다. 해시 재정리 작업에 들어가면 내부에 갖고 있는 자료 구조를 다시 생성하는 단계를 거쳐야 하므로 성능에 영향이 발생한다.

3. HashSet의 주요 메소드

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:-----:|:----------------:|:--:|
|boolean|add(E e)|데이터를 추가한다.|
|void|clear()|모든 데이터를 삭제한다.|
|Object|clone()|HashSet 객체를 복사한다.|
|boolean|contains(Object o)|지정한 객체가 존재하는 지를 확인한다.|
|boolean|isEmpty()|데이터가 있는지 확인한다.|
|Iterator< E >|iterator()|데이터를 꺼내기 위한 Iterator 객체를 리턴한다.|
|boolean|remove(Object o)|매개 변수로 넘어온 객체를 삭제한다.|
|int|size()|데이터의 개수를 리턴한다.|

### 8. Queue
1. LinkedList 클래스
    - LinkedList에서는 앞의 데이터와 뒤에 있는 데이터만 기억한다.
    - 중간에 있는 데이터가 지속적으로 삭제되고 추가될 경우에 배열보다 메모리 공간 측면에서 훨씬 유리하다.
    - 배열은 각 위치가 정해져 있고 값을 삭제하면 그 뒤에 있는 값들은 하나씩 앞으로 위치를 이동해야하지만 LinkedList는 중간에 있는 데이터 삭제하면, 지운 데이터의 앞에 있는 데이터와 뒤에 있는 데이터를 연결하면 된다.
    - LinkedList는 List 인터페이스뿐만 아니라 Queue와 Deque 인터페이스도 구현하고 있다. LinkedList 자체가 List이면서도 Queue,Deque도 된다.

2. Queue
    - FIFO(First In First Out)
    - 사용자들의 요청을 순서대로 처리할 때 사용
    - Deque : Queue 인터페이스를 확장하였기 때문에 Queue의 기능을 전부 포함한다. 맨 앞과 뒤를 넣거나 빼는 작업을 수행하는데 용이하도록 되어있다.

3. LinkedList의 상속관계
- java.lnag.Object
- -> java.util.AbstractCollection< E >
- -> java.util.AbstractList< E >
- -> java.util.AbstractSequentialList< E >
- -> java.util.LinkedList< E >

4. LinkedList의 생성자
|생성자|설명|
|:--:|:--:|
|LinkedList()|비어 있는 LinkedList 객체를 생성한다.|
|LinkedList(Collection<? extends E> c)|매개 변수로 받은 컬렉션 객체의 데이터를 LinkedList에 담는다.|

5. LinkedList의 메소드

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:------:|:----------------:|:-:|
|void|addFirst(Object)|LinkedList 객체의 가장 앞에 데이터를 추가 한다.|
|boolean|offerFirst(Object)|LikedList 객체의 가장 앞에 데이터를 추가한다.|
|void|push(Object)|LikedList 객체의 가장 앞에 데이터를 추가한다.|
|boolean|add(Object)|LinkedList 객체의 가장 뒤에 데이터를 추가한다.|
|void|addLast(Object)|LinkedList 객체의 가장 뒤에 데이터를 추가한다.|
|boolean|offer(Object)|LinkedList 객체의 가장 뒤에 데이터를 추가한다.|
|boolean|offerLast(Object)|LinkedList 객체의 가장 뒤에 데이터를 추가한다.|
|void|add(int,Object)|LinkedList 객체의 특정 위치에 데이터를 추가한다.|
|Object|set(int,Object)|LinkedList 객체의 특정 위치에 있는 데이터를 수정한다. 그리고, 기존에 있던 데이터를 리턴한다.|
|boolean|addAll(Collection)|매개 변수로 넘긴 컬렉션의 데이터를 추가한다.|
|boolean|addAll(int, Collection)|매개 변수로 넘긴 컬렉션의 데이터를 지정된 위치에 추가한다.|

### 9. Map

1. Map의 특징
    1. 모든 데이터는 키와 값이 존재한다.
    2. 키가 없이 값만 저장될 수는 없다.
    3. 값 없이 키만 저장할 수도 없다.
    4. 키는 해당 Map에서 고유해야만 한다.
    5. 값은 Map에서 중복되어도 상관없다.


