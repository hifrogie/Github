## 6. selector
### 1. objective-c
1. selector의 타입은 objective-c
2. #selector라는 표현식으로 나타낼 수 있다.
3. getter, setter
    1. #selector(getter: MyViewController.myButton)
4. 오버로딩된 함수를 사용할 때는 as를 사용해서 확실히 하시오
5. key
    1. 객체의 특정 속성을 식별하는 문자열
    2. 키 경로는 도트로 분리된 키의 문자열로 통과할 객체 속성의 시퀸스를 지정합니다. 키 및 키 경로는 문자열 식별자를 사용하여 객체의 속성 및 관계에 직접적으로 액세스 하기 위한 메커니즘인 키-값 코딩(KVC)에 자주 사용됩니다.