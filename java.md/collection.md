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
    - thread safe : 멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 혹은 객체가 여러 스레드로 부터 동시에 접근이 이루어져도 프로그램의 실행에 문제가 없음
    - 멀티 쓰레딩(multi-threading) : 하나의 프로세스 내에서 여러 스레드가 동시에 작업을 수행하는 것
    - 프로세스 : 실행중인 프로그램
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
### 5. ArrayList와 LinkedList의 차이
1. LinkedList는 ArrayList와 달리 List인터페이스를 구현한 AbstractList를 상속하지 않고 AbstractSequentialList를 상속하고 있습니다.
2. ArrayList는 데이터들이 순서대로 쭉 늘어선 배열의 형식을 취하고 있는 반면 LinkedList는 자료의 주소 값으로 서로 연결되어 있는 구조이다.
3. ArrayList에서는 무작위 접근(random access)이 가능하지만, LinkedList에서는 순차 접근(sequential access)만 가능합니다.
4. 특히, 단순 LinkedList는 단방향성을 가지고 있기 때문에 인덱스를 이용하여 자료를 검색하는 앱에는 적합하지않다.
5. n개의 자료를 저장할 때, ArrayList는 자료들을 하나의 연속적인 묶음으로 묶어 자료를 저장하는 반면, LinkedList는 자료들을 저장 공간에 불연속적인 단위로 저장하게 됩니다. 그래서 LinkedList는 메모리 이곳저곳에 산재해 저장되어있는 노드들을 접근하는데 ArrayList보다는 긴 지연 시간이 소모됩니다.
6. LinkedList의 또 다른 단점은 참조자를 위해 추가적인 메모리를 할당해야하는  점입니다. 
### 6. Stack 클래스
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
### 7. Stack이 Vector을 상속받아서 망한 이유
1. Vector의 단점
    - get,set,forEach,add()메소드가 모두 synchronized되어 있다.
    - 그래서 사용시 오버헤드가 발행한다.
    - 오버헤드(overhead) : 어떤 처리를 하기 위해 들어가는 간접적인 처리 시간 및 메모리
    - 멀티쓰레드 환경에서 안전히 사용할 수 있지만 그외의 환경에서는 성능저하가 일어난다.
    - 하지만 ArrayList도 멀티쓰레드 환경에서 쓸 수 있고 Vector보다 좋은 성능을 가지고 있기 때문에 Vector 보다는 ArrayList를 쓰는 것이 좋다.
### 8. Set
1. Set이 왜 필요하지?
 - 중복되는 것을 방지하고 순서에 상관없이 어떤 데이터가 존재하는지 확인하기 위한 용도로 사용

 2. Set 인터페이스를 구현한 주요 클래스
    - HashSet : 순서가 전혀 필요없는 데이터를 hash table에 저장한다, Set중에 가장 성능이 좋다.
    - TreeSet : 저장된 데이터의 값에 따라서 정렬되는 셋이다. red-black이라는 트리 타입으로 값이 저장되며 HashSet보다 성능이 느리다.
    - LinkedHashSet : 연결된 목록 타입으로 구현된 해시 테이블에 테이터를 저장한다. 저장된 순서에 따라서 값이 정렬된다. 성능은 제일 나쁘다.

### 9. Hash란 무엇인가?
1. 내부적으로 배열을 사용하여 데이터를 저장하기 때문에 빠른 검색속도를 갖는다.
2. 데이터 추가/삭제시 기존 데이터를 밀어내거나 당기는 작업이 필요없도록 특별한 알고리즘을 이용하여 데이터와 연관된 고유한 숫자를 만들어 낸뒤 이를 인덱스로 사용한다.
3. 특정 데이터가 저장되는 인덱스를 그 데이터만의 고유한 위치로 정하여서 데이터 추가/삭제시 데이터의 이동이 없도록 만들어진 구조이다.
4. Hash Table
    - Hash가 내부적으로 사용하는 배열을 Hash Table 이라고 하며 크기에 따라 성능 차이가 날 수있다.
    - key-value에서 key를 테이블에 저장할 때 key값을 Hash Method를 이용해 계산을 수행한 후, 그 결과값을 배열의 인덱스로 사용하여 저장하는 방식이다. 
    - 여기서 key값을 계산하는 것이 Hash Method이다.
5. Hash Method
    - Hash는 특별한 알고리즘을 이용하여 데이터의 고유한 숫자값을 만들어 인덱스로 사용한다고 했다.
    - 이 알고리즘을 구현한 메소드를 Hash Method라고 하며 이 메소드에 의해 반환된 데이터의 고유 숫자값을 Hash Code 라고 한다.
    - 자바에서는 Object클래스의 hashCode()메소드를 이용하여 모든 객체의 Hahs Code를 쉽게 구할 수있다.
    - Hash Method를 이용해서 데이터를 Hash Table에 저장하고 검색하는 기법을 Hashing이라 한다.
    - Hash Method는 데이터가 저장되어 있는 곳을 알려주기 때문에 다량의 데이터 중에서도 원하는 데이터를 빠르게 찾을 수 있다.
6. Hashing
    - HashMap과 같이 Hashing을 구현한 컬렉션 클래스에서는 Object클래스에 정의된 hashCode()를 Hash Method로 사용한다.
    - Object 클래스에 정의된 hashCode()는 객체의 주소를 이용하는 알고리즘으로 해시 코드를 만들어내기 때문에 모든 객체에 대해 중복되지 않는 값을 제공한다.
    - String클래스의 경우 Object로 부터 상속받은 hashCode()를 오버 라이딩하여 문자열의 내용으로 해시 코드를 만들어 낸다.
    - 서로다른 Stirng 인스턴스 일지라도 같은 내용의 문자열을 가졌다면 hashCode()를 호출했을 때 같은 값을 갖는다.
7. HashMap에서 중복검사등을 담당하는 것이 Hash
8. Hash는 key-value를 HahTable에 저장한다. 이때 저장할 key를 HashMethod인 hashCode()를 사용해 중복없는 고유의 값으로 만든다.
9. 방법은 String 클래스를 보면 알 수 있다. 
    - String 클래스에서 값이 입력되면 Object의 hashCode()를 오버라이딩하여 해당 값을 코드로 변환한다. 
    - 그렇기 때문에 서로 다른 String 객체라도 입력된 값이 같다면 hashCode는 동일한 코드를 반환한다. 
    - 이때 String 클래스의 equals()로 두 객체를 비교하면 값도 같고 hashCode도 동일하기 때문에 같은 객체로 인지하게 되는 것이다.
    - 이 방법 그대로 HashTable에 key를 저장할 때 HashCode()를 사용하여 특정 코드로 변환하고 변환된 코드를 저장한다.
    - 같은 key값이 들어오면 hashCode로 변환 후 같은 값을 찾아 덮어쓴다.
    - 이렇게 HashMethod를 써서 HashTable에 저장하는 것을 Hashing이라고 한다.
10. Hash 충돌
    - 해시함수는 출력값은 유한하고 입력값은 무한하기 때문에 충돌이 발생한다.
    - 즉, 서로 다른 입력값이 같은 출력값을 가질 수 있다.
    - 이를 회피하기 위한 방법으로 개별 체이닝 방법과 오픈 어드레싱이 있다.
    - 개별 체이닝(Separate Chaining)
        - 충돌 발생 시 같은 인덱스를 Linked List로 연결하는 방식
        - 원리
            1. 키의 해시 값을 계산
            2. 해시 값을 이용해 배열의 인덱스를 구합니다.
            3. 같은 인덱스가 있다면 연결 리스트로 연결합니다.
        - 개별 체이닝의 문제점 
            1. 대부분의 탐색은 O(1)이지만 최악의 경우, 모든 해시 충돌이 발생했다고 가정할 경우 O(n)이 된다. 
            2. 자바 8에서는 연결리스트 구조를 좀 더 최적화해서, 데이터의 개수가 많아지면 레드-블랙 트리에 저장하는 형태로 병행해 사용하기도 했습니다.
    - 오픈 어드레싱 (Open Addressing)
        - 충돌 발생 시 탐사를 통해 빈 공간을 찾아나서는 방식이다.
        - 전체 슬롯의 개수 이상은 저장할 수 없다.
        - 충돌이 일어나면 테이블 공간 내에서 탐사를 통해 빈 공간을 찾기에, 개별 체이닝 방식과는 다르게 모든 원소가 반드시 자신의 해시 값과 일치하는 주소에 저장된다는 보장도 없다.
        - 오픈 어드레싱 방식에는 여러가지가 존재하는데 가장 간단한 방식인 선형 탐사 방식(Linear Probing)을 소개하겠다.
        - 선형 탐사 방식은 충돌이 발생할 경우 해당 위치부터 순차적으로 탐사를 하나씩 진행합니다.
        - 특정 위치가 선점되어 있으면 바로 그 다름 위치를 확인하는 식입니다.
        - 이렇게 탐사를 진행하다가 비어 있는 공간을 발견하면 삽입하게 됩니다.
        - 즉, 가장 가까운 다음 빈 위치를 탐사해 새 키를 삽입하는 것입니다.
        - 단점 
            - 해시 테이블에 저장되는 데이터들이 고르게 분포되지 않고 뭉치는 경향이 있다.
            
### 10. HashSet
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

### 11. Queue
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

### 12. Map

1. Map의 특징
    1. 모든 데이터는 키와 값이 존재한다.
    2. 키가 없이 값만 저장될 수는 없다.
    3. 값 없이 키만 저장할 수도 없다.
    4. 키는 해당 Map에서 고유해야만 한다.
    5. 값은 Map에서 중복되어도 상관없다.

### 13. HashMap, Hashtable, ConcurrentHashMap
1. Map 인터페이스의 구현체이다.
2. HashMap
    1. key와 value에 null을 허용한다.
    2. 동기화를 보장하지 않는다.
    3. HashMap은 thread-safe 하지 않아, 싱글 쓰레드 환경에서 사용하는 게 좋다.
    4. 동기화 처리를 하지 안히 때문에 데이터를 탄색하는 속도가 빠르다.
    5. 동기화 : 프로세스(스레드)가 수행되는 시점을 조절하여 서로가 알고 있는 정보가 일치하는 것
    6. 결국, HashTable과 ConcurrentHashMap보다 데이터를 찾는 속도는 빠르지만, 신뢰성과 안정성이 떨어진다.
3. HashTable
    1. key와 value에 null을 허용하지 않는다.
    2. 동기화를 보장한다.
    3. HashTable은 thread-safe하기 때문에, 멀티 쓰레드 환경에서 사용할 수있습니다. 이는 데이터를 다루는 메소드(get(),put(),remove()등)에 synchronized 키워드가 붙어 있다. 
    4. 해당 키워드는 메소드를 호출하기전에 쓰레드간 동기화 락을 건다.
    5. 그래서 멀티 쓰레드 환경에서도 데이터의 무결성을 보장한다.
    6. 쓰레드간 동기화 락은 매우 느린 동작이라는 단점이 있다.
4. ConcurrentHashMap
    1. key와 value에 null을 허용하지 않는다.
    2. 동기화를 보장한다.
    3. ConcurrentHashMap은 thread-safe하기 때문에, 멀티 쓰레드 환경에서 사용할 수있다.
    4. 이 구현체는 HashMap의 동기화 문제를 보완하기 위해 나타났다.
    5. 동기화 처리를 할 때, 어떤 Entry를 조작하는 경우에 해당 Entry에 대해서만 락을 건다. 그래서 HashTable보다 데이터를 다루는 속도가 빠르다.
    6. Entry 아이템 별로 락을 걸어 멀티 쓰레드 환경에서의 성능을 향상시킨다. 
    7. Entry
        - Map.Entry는 Map형태의 인터페이스를 만드는 데 사용한다.
        - 실제 사용은 아래와 같이 Map을 For문에서 돌려줄 경우, 인터페이스 용도로 사용하거나
        - stream 사용시 Map 형식의 데이터에서 처리가 필요할 때 Map.Entry를 사용하여 처리하게 된다.
        
![엔트리](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FZYadc%2FbtriYpaxdw0%2F2ytECKtedpewiV1BWdVVv1%2Fimg.png)

### 14. Big-O 표기법
1. Big-O notation
    - 알고리즘의 시간 복잡도를 나타내는 표기법이며, O(f(n))으로 나타낸다.
2. 시간 복잡도는 다음과 같은 순서로 빠르다.
    - O(1) > O(logn) > O(n) > O(nlogn) > O(n^c) > O(c^n) > O(n!)
3. 빅오 표기법의 특징
    - O(2) → O(1)
    - O(2n) → O(n)
    - O(3n^2 + 2n + 3) → O(n^2)
    - 상수항을 없애고, 하위 항들은 제거해야함.

### 15. 배열과 리스트
1. 배열
    1. 배열 특징
        1. 인덱스(논리적 순서)와 메모리 주소(물리적 순서)가 동일하다.
        2. 연관된 데이터를 하나의 변수에 그룹핑해서 관리하기 위한 선형 자료구조
        3. 데이터의 개수가 정해져있는 경우나 데이터의 수정이 적은 경우, 데이터의 검색이 빈번한 경우에 사용한다.
        4. 데이터가 연속된 메모리 공간에 순차적으로 저장된다.
    2. 배열에서의 시간 복잡도
        1. 삽입/삭제
            - 배열의 맨 앞에 삽입/삭제:O(n)
            - 배열의 맨 뒤에 삽입/삭제: O(1)
            - 배열의 중간에 삽입/삭제: O(n)
        2. 탐색
            - O(1)
    3. 배열의 장점
        1. 인덱스를 가져서 값에 바로 접근이 가능하다.
        2. 연속된 메모리 공간에 존재하여 관리가 수월하다.
    4. 배열의 단점
        1. 삽입과 삭제가 어렵고 처음 생성할 때 크기를 선언해서 크기가 가변이 아니다.
        2. 배열에서 데이터의 삽입과 삭제는 해당 위치에서 작업 이후 해당 원소 뒤의 모든 원소들에서 이동이 이루어지기 때문에 시간이 오래 걸린다.
        3. 인덱스가 삭제되어도 인덱스를 유지해야하기 때문에 해당 메모리를 유지해야한다. 그래서 초기에 적절한 배열의 크기를 선언하지 않으면 메모리의 낭비를 초래하게 된다.
2. 리스트
    1. 리스트 특징
        1. 리스트와 배열의 가장 큰 차이는 인덱스의 유무
        2. 리스트는 메모리 낭비를 줄이기 위해 인덱스를 포기하고 노드를 연결해 데이터를 적재하는 형태의 선형 자료구조이다.
        3. 불연속적인 메모리 공간에 원소와 다음 노드의 주소를 가진 노드가 계속해서 이어져 있어 선형의 형태를 유지하는 것이다.
        4. 원소의 삽입과 삭제가 빈번하거나, 자료의 검색이 빈번하지 않은 경우에 사용한다.
        5. 리스트는 노드들을 연결하여 만든 것으로 노드는 기본적으로 헤드와 테일의 형태로 이루어져있다.
        6. 각 노드의 테일에는 다음 노드의 주소 정보를 저장하고 있어 데이터가 불연속적인 메모리 공간에 위치하고 있어도 꼬리에 꼬리를 물고 원하는 원소에 접근이 가능하다.
        7. 그렇기 때문에 크기가 고정되어 있지 않고 새로운 원소를 추가할 경우, 테일 노드에 새롭게 추가된 원소의 주소를 연결해주면된다.
    2. 리스트에서의 시간 복잡도
        1. 삽입
            1. 리스트의 맨 앞에 삽입: O(1)
            2. 리스트의 중간에 삽입: O(n)
        2. 삭제
            1. 리스트의 맨 뒤에 삽입/삭제 : O(1)
            2. 리스트의 중간에서 삭제 : O(n)
        3. 탐색
            1. O(n)
            2. 인덱스 접근이 불가능해서 리스트 처음부터 링크를 타고 순차적으로 탐색해야 하기 때문
    3. 리스트의 장점
        1. 원소의 추가와 삭제에 따라 크기가 동적으로 변하기 때문에 연속적으로 메모리를 할당할 필요가 없고, 사용한 메모리도 재사용이 가능하여 메모리의 낭비가 적다.
        2. 크기가 가변이다.
    4. 리스트의 단점
        1. 인덱스가 없다.
        2. 탐색이 순차적으로 이루어져 탐색 시간이 길다.
        3. 별도의 주소를 저장하는 공간을 필요로 하여 추가적인 메모리가 필요하다.
