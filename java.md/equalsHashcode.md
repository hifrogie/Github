## 3. equals, hashCode에 대해서
### 1. equals, hashCode가 왜 중요한가?
 #### 1. equals() 메소드 란?
   1. 매개변수로 들어오는 객체와 자신의 객체가 같은지 비교하는 기능
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
        - 주소 값이 다르면 String 객체의 문자열 Char 타입으로 하나씩 비교해 보면서 끝까지 같다면 true를 리턴, 다르다면 false를 리턴한다.
  #### 2. hashCode()란?
   1. hashCode()는 객체의 hashCode를 리턴한다.
   2. hashCode는 일반적으로 각 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값
### 2. equals와 hashCode는 동시에 오버라이드 되어야한다. 
   1. 동일한 객체는 동일한 메모리 주소를 갖는다는 것을 의미 하므로, 동일한 객체는 동일한 해시코드를 가져야한다.
### 3. equals와 hashCode의 관계
   1. Java 프로그램을 실행하는 동안 equals에 사용된 정보가 수정되지 앟았다면, hashCode는 항상 동일한 정수값을 반환해야한다.(프로그램을 실행할 때 마다 달라지는 것은 상관이 없다.)
   2. 두 객체가 equals()에 의해 동일하다면, 두 객체의 hashCode() 값도 일치해야 한다.
   3. 두 객체가 equals()에 의해 동일하지 않다면 두 객체의 hashCode()값은 일치하지 않아도 된다.
### 4. Hashcode 중요한 이유
   1. 객체를 비교할 때 드는 비용을 낮추기 위해서 사용한다.
   2. equals()를 사용하면 Integer를 비교하는 것에 비해 많은 시간이 소요된다.
### 5. equals, hashCode의 차이점
   1. equals는 비교하는 것이고 hashCode는 고유한 숫자를 나타내는 것이다.
### 6. 구현하는 방법
   1. Object에 명시되어있기 때문에 그냥 사용하거나 overriding해서 사용한다.

   ```java
   public final class String {
    private final char value[];

    public int hashCode() {
        int h = hash;
        if (h == 0 && value.length > 0) {
            char val[] = value;

            for (int i = 0; i < value.length; i++) {
                h = 31 * h + val[i];
            }
            hash = h;
        }
        return h;
    }
   }
   ```
### 7. equals를 재정의한 클래스에서 hashcode를 재정의하지 않을 때
   1. hash를 사용하는 HashMap, HashSet과 같은 컬랙션의 원소로 사용될 때 문제가 발생한다.
