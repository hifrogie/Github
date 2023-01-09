## 3. 데이터 타입
### 1. Any
1. Any는 스위프트의 모든 데이터 타입을 사용할 수 있다는 뜻

### 2. AnyObject
1. Any보다는 한정된 의미로 클래스의 인스턴스만 할당 가능
2. Any나 AnyObject 잘 안써야하는 이유
    1. Any로 선언된 변수의 값을 가져다 쓰려면 매번 타입 확인 및 변환을 해줘야한다.
    2. 예기치 못한 에러 발생가능

### 3. nil
1. 없음을 나타내는 스위프트의 키워드

### 4. 타입 별칭
1. 이미 존재하는 데이터 타입에 임의로 별칭을 부여할 수 있다.
```swift
typealias MyInt = Int

let age: MyInt = 100
```

### 5. 튜플(Tuple)
1. 튜플은 타입의 이름이 따로 저장되어 있지 않은 프로그래머 마음대로 만드는 타입입니다.
2. 지정된 데이터 묶음이라고 표현 가능

```swift
var person: (String, Int, Double) = ("yagom", 100, 182.5)

//인덱스를 이용해서 값을 뺄 수 있다.
print("이름: \(person.0), 나이: \(person.1), 신장: \(person.2)")

person.1 = 99
person.2 = 178.5 //인덱스를 통해 값을 할당 가능
```

### 6. 컬렉션형 : 배열
1. 배열은 같은 타입의 데이터를 일렬로 나열 후 순서대로 저장하는 형태의 컬렉션 타입
2. 다른 위치에 같은 값 들어갈 수 있다.

```swift
var names: Array<String> = ["yagom", "chulsoo", "younghee", "yagom"]

var names: [String] = ["yagom", "chulsoo", "younghee", "yagom"]

//Any 데이터를 요소로 갖는 빈 배열을 생성
var emptyArray: [Any] = [Any]()
var emptyArray: [Any] = Array<Any>()

// 배열의 타입을 정확히 명시했다면 []만으로 빈 배열 생성가능
var emptyArray: [Any] = []
print(emptyArray.isEmpty)
print(names.count)
```

3. firstIndex(of: ) 
    1. 맨 앞에 인덱스를 알아낼 수 있다. 
4. append(_: )
    1. 맨 뒤에 요소를 추가하고 싶을 때 사용
5. insert(_:at:)
    1. 중간에 요소를 삽입하고 싶다면 사용
6. remove(_:)
    1. 요소를 삭제하고 싶을 때 사용

### 7. 컬렉션 형 : 딕셔너리
1. 딕셔너리는 요소들이 순서 없이 키와 값의 쌍으로 구성되는 컬렉션 타입입니다.
2. 딕셔너리 안에는 키가 하나이거나 여러개 일 수 있습니다.
3. 단 하나의 딕셔너리 안의 키는 같은 이름을 중복해서 사용할 수 없습니다.

```swift
typealias StringIntDictionary = [String: Int]

//키는 String, 값은 Int 타입인 빈 딕셔너리를 생성합니다.
var numberForName: Dictionary<String, Int> = Dictionary<String, Int>()

var numberForName: [String: Int] = [String: Int]()

var numberForName: StringIntDictionary = StringIntDictionary()

var numberForName: [String: Int] = [:]

var numberForName: [String: Int] = ["yagome": 100, "chulsoo":200,"jenny":300]

print(numberForName.isEmpty)
print(numberForName.count)
```

### 8. 컬렉션 형 : 세트
1. 세트는 같은 타입의 데이터를 순서 없이 하나의 묶음으로 저장하는 형태의 컬렉션 타입입니다.
2. 세트 내에는 중복 된 값이 존재하지 않는다.
3. 세트는 순서가 중요하지 않거나 각 요소가 유일한 값이어야 하는 경우에 사용합니다.
4. 세트의 요소로는 해시 가능한 값이 들어와야 함
5. 배열과 달리 축약형이 없다.

```swift
var names: Set<String> = Set<String>()
var names: set<String> = []

var names: Set<String> = ["yagom", "chulsoo", "younghee"]
```
