# 어려운 질문들
## 목차
1. [다형성]()
2. [동일성 vs 동등성이 무엇인가?]()
3. [equals, hashCode에 대해서]()
4. [enum 클래스의 메모리 구조]()
### 1. 다형성
1. 다형성(polymorphism)이란?
    1. 부모-자식 상속 관계에 있는 클래스에서 상위클래스가 동일한 메세지로 하위 클래스들을 서로 다르게 동작시키는 객체 지향 원리
    2. 부모 클래스가 자식 클래스의 동작 방식을 알수 없어도 오버라이딩을 통해 자식 클래스에 접근할 수 있다.
    3. 동적바인딩 덕분에 부모가 자식이 어떤 일을 하는 지 몰라도, 자식 멤버 함수를 호출시킬 수 있다.
        1. 동적 바인딩 : 실행 시간 (Runtime) 즉, 파일을 실행하는 시점에 성격이 결정된다. 실제 참조하는 객체의 메소드를 호출한다.
    4. 하나의 객체가 여러 가지 타입을 가질 수 있는 것을 의미한다. 
2. 다형성의 장점
    1. 여러 객체를 하나의 타입으로 관리가 가능하기 때문에 코드 관리가 편리해 유지보수가 쉽다.
    2. 다형성을 활용하면 객체를 재사용하기 쉬워지기 때문에 코드 재사용성이 높아집니다.
    3. 클래스간의 의존성이 줄어들어 확장성이 높고 결합도가 낮아져 안전성이 높아집니다.
3. 다형성 필수 조건
    1. 클래스 상속이 이루어져야됨
    2. 오버라이딩 필수
    3. 부모 타입으로 자식 클래스를 업캐스팅하여 객체를 생성해야 합니다.
4. 다형성 구현 방법
    1. 상속 클래스 구현
    2. 메소드 오버라이딩
    3. 업캐스팅하여 객체 선언
    4. 부모 클래스 객체로 자식 메소드 호출

### 2. 동일성 vs 동등성이 무엇인가?
1. 동일성(identity)
    1. 두 객체가 완전히 같은 경우를 의미한다.
    2. 사실상 하나의 객체로 봐도 무방하다.
    3. 주소 값이 같기에 두 변수가 같은 객체를 가리키게 된다.
    4. ==
2. 동등성(equality)
    1. 두개의 객체가 같은 정보를 갖고 있는 경우를 의미한다.
    2. 변수가 참조하고 있는 객체의 주소가 서로 다르더라도 내용만 같으면 두변수는 동등하다고 이야기할 수 있다.
    3. System.out.println(str1.equals(str2));

### 3. equals, hashCode에 대해서
1. equals, hashCode가 왜 중요한가?
    1. equals() 메소드 란?
        1. 메개변수로 들어오는 객체와 자신의 객체가 같은지 비교하는 기능
        2. equals()는 Object에 포함되어 있기 때문에 모든 하위 클래스에서 재정의 해서 사용이 가능하다.
        3. ==는 주소값이 같은지 아닌지 비교하는 것이고, equals()연산도 내부적으로 주소값을 비교하지만 String클래스에서는 equals()를 재정의해 내용을 비교하게 되어있다.
        4. 코드
        ```java
        public boolean equals(Object obj){
            return (this == obj);
        }
        ```
        5. equals()도 내부적으로는 == 연산자를 사용해 주소를 비교하는 것과 다름이 없다. 
        6. 주소를 비교하는 것이 아닌 내용을 비교하는 String 클래스의 equals()
        ```java
        public boolean equals(Object anObject){
            if(this == anObject){
                return true;
            }
            if (anObject instanceof String){
                String anotherString = (String)anObject;
                int n = value.length;
                if (n == anotherString.value.length){
                    char v1[] = value;
                    char v2[] = anotherString.value;
                    int i = 0;
                    while (n-- != 0){
                        if (v1[i] != v2[i])
                            return false;
                        i++;
                    }
                    return true;
                }
            }
            return false;
        }
        ```
        - equals()변수로 들어온 객체가 자기 자신과 주소값이 같으면 if(this == anObject) true를 리턴한다.
        - 주소 값이 다르면 String 객체의 문자열 Char 타입으로 하나씩 비교해 보면서 끝까지 같다면 true를 리턴 다르다면 false를 리턴한다.
    2. hashCode()란?
        1. hashCode()는 객체의 hashCode를 리턴한다.
        2. hashCode는 일반적으로 각 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값
2. equals와 hashCode는 동시에 오버라이드 되어야한다. 
    1. 동일한 객체는 동일한 메모리 주소를 갖는다는 것을 의미 하므로, 동일한 객체는 동일한 해시코드를 가져야한다.
3. equals와 hashCode의 관계
    1. Java 프로그램을 실행하는 동안 equals에 사용된 정보가 수정되지 앟았다면, hashCode는 항상 동일한 정수값을 반환해야한다.(프로그램을 실행할 때 마다 달라지는 것은 상관이 없다.)
    2. 두 객체가 equals()에 의해 동일하다면, 두 객체의 hashCode() 값도 일치해야 한다.
    3. 두 객체가 equals()에 의해 동일하지 않다면 두 객체의 hashCode()값은 일치하지 않아도 된다.
4. 중요한 이유
    1. 같은 값인지 비교하기 위해서 중요하다.
5. equals, hashCode의 차이점
    1. equals는 비교하는 것이고 hashCode는 고유한 숫자를 나타내는 것이다.
6. 구현하는 방법
    1. Object에 명시되어있기 때문에 그냥 사용하거나 overriding해서 사용한다.

### 4. enum 클래스의 메모리 구조
1. enum과 메모리 구조
    1. 열거 상수는 상수 각각을 내부적으로 public static final 필드 이면서 객체로 제공되도록 합니다.
    2. static이 붙어있기 때문에 각각의 상수는 클래스 변수로 클래스 로더가 로드 시점에 JVM Method 영역에 해당 클래스 변수들을 항상 상주시켜 프로그램이 종료되기 전에는 언제든 가져다 쓸 수 있는 주소 공간을 확보합니다.
    ![메소드 영역 이미지](https://honbabzone.com/assets/images/post/java/emum-memory.png)
