### 목차
### 1. [다형성](https://github.com/hifrogie/Github/blob/main/java.md#1-%EB%8B%A4%ED%98%95%EC%84%B1-1)
1. [다형성이란?](https://github.com/hifrogie/Github/blob/main/java.md#1-%EB%8B%A4%ED%98%95%EC%84%B1polymorphism%EC%9D%B4%EB%9E%80)
2. [다형성의 장점](https://github.com/hifrogie/Github/blob/main/java.md#2-%EB%8B%A4%ED%98%95%EC%84%B1%EC%9D%98-%EC%9E%A5%EC%A0%90)
3. [다형성 필수 조건](https://github.com/hifrogie/Github/blob/main/java.md#3-%EB%8B%A4%ED%98%95%EC%84%B1-%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4)
4. [다형성 구현 방법](https://github.com/hifrogie/Github/blob/main/java.md#4-%EB%8B%A4%ED%98%95%EC%84%B1-%EA%B5%AC%ED%98%84-%EB%B0%A9%EB%B2%95)
### 2. [동일성 vs 동등성이 무엇인가?](https://github.com/hifrogie/Github/blob/main/java.md#2-%EB%8F%99%EC%9D%BC%EC%84%B1-vs-%EB%8F%99%EB%93%B1%EC%84%B1%EC%9D%B4-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-1)
1. [동일성](https://github.com/hifrogie/Github/blob/main/java.md#1-%EB%8F%99%EC%9D%BC%EC%84%B1identity)
2. [동등성](https://github.com/hifrogie/Github/blob/main/java.md#2-%EB%8F%99%EB%93%B1%EC%84%B1equality)
### 3. [equals, hashCode에 대해서](https://github.com/hifrogie/Github/blob/main/java.md#3-equals-hashcode%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-1)
1. [equals, hashCode가 왜 중요한가?](https://github.com/hifrogie/Github/blob/main/java.md#1-equals-hashcode%EA%B0%80-%EC%99%9C-%EC%A4%91%EC%9A%94%ED%95%9C%EA%B0%80)
2. [equals와 hashCode는 동시에 오버라이드 되어야한다](https://github.com/hifrogie/Github/blob/main/java.md#2-equals%EC%99%80-hashcode%EB%8A%94-%EB%8F%99%EC%8B%9C%EC%97%90-%EC%98%A4%EB%B2%84%EB%9D%BC%EC%9D%B4%EB%93%9C-%EB%90%98%EC%96%B4%EC%95%BC%ED%95%9C%EB%8B%A4)
3. [equals와 hashCode의 관계](https://github.com/hifrogie/Github/blob/main/java.md#3-equals%EC%99%80-hashcode%EC%9D%98-%EA%B4%80%EA%B3%84)
4. [중요한 이유](https://github.com/hifrogie/Github/blob/main/java.md#4-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0)
5. [equals, hashCode의 차이점](https://github.com/hifrogie/Github/blob/main/java.md#5-equals-hashcode%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90)
6. [구현하는 방법](https://github.com/hifrogie/Github/blob/main/java.md#6-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
### 4. [enum 클래스의 메모리 구조](https://github.com/hifrogie/Github/blob/main/java.md#4-enum-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0-1)
1. [enum과 메모리 구조](https://github.com/hifrogie/Github/blob/main/java.md#1-enum%EA%B3%BC-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0)
### 5. [예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception)
 1. [예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception-1)
 2. [try-catch](https://github.com/hifrogie/Github/blob/main/java.md#2-try-catch)
 3. [예외의 종류는 3가지](https://github.com/hifrogie/Github/blob/main/java.md#3-%EC%98%88%EC%99%B8%EC%9D%98-%EC%A2%85%EB%A5%98%EB%8A%94-3%EA%B0%80%EC%A7%80)
 4. [java.lang.Throwable](https://github.com/hifrogie/Github/blob/main/java.md#4-javalangthrowable)
 5. [Throwable의 생성자](https://github.com/hifrogie/Github/blob/main/java.md#5-throwable%EC%9D%98-%EC%83%9D%EC%84%B1%EC%9E%90)
 6. [Throwable클래스에 선언되어있고, Exception클래스에서 Overriding한 메소드](https://github.com/hifrogie/Github/blob/main/java.md#6-throwable-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90-%EC%84%A0%EC%96%B8%EB%90%98%EC%96%B4-%EC%9E%88%EA%B3%A0-exception-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-overriding%ED%95%9C-%EB%A9%94%EC%86%8C%EB%93%9C)
 7. [throw와 throws](https://github.com/hifrogie/Github/blob/main/java.md#7-throw%EC%99%80-throws)
 8. [예외 만들기](https://github.com/hifrogie/Github/blob/main/java.md#7-throw%EC%99%80-throws)
 9. [자바 예외 처리 전략](https://github.com/hifrogie/Github/blob/main/java.md#9-%EC%9E%90%EB%B0%94-%EC%98%88%EC%99%B8-%EC%B2%98%EB%A6%AC-%EC%A0%84%EB%9E%B5)
### 6. [String](https://github.com/hifrogie/Github/blob/main/java.md#6-string)
1. [String클래스 선언부](https://github.com/hifrogie/Github/blob/main/java.md#1-string-%ED%81%B4%EB%9E%98%EC%8A%A4-%EC%84%A0%EC%96%B8%EB%B6%80)
2. [String 생성자](https://github.com/hifrogie/Github/blob/main/java.md#2-string-%EC%83%9D%EC%84%B1%EC%9E%90)
3. [null check](https://github.com/hifrogie/Github/blob/main/java.md#3-null-check)
4. [String의 메소드](https://github.com/hifrogie/Github/blob/main/java.md#4-string%EC%9D%98-%EB%A9%94%EC%86%8C%EB%93%9C)
5. [StringBuffer와 StringBuilder](https://github.com/hifrogie/Github/blob/main/java.md#5-stringbuffer%EC%99%80-stringbuilder)
### 7. [Nested 클래스](https://github.com/hifrogie/Github/blob/main/java.md#7-nested-%ED%81%B4%EB%9E%98%EC%8A%A4)
1. [Nested 클래스](https://github.com/hifrogie/Github/blob/main/java.md#1-nested-%ED%81%B4%EB%9E%98%EC%8A%A4)
2. [Static nested 클래스의 특징](https://github.com/hifrogie/Github/blob/main/java.md#2-static-nested-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%9D%98-%ED%8A%B9%EC%A7%95)
3. [내부 클래스와 익명 클래스](https://github.com/hifrogie/Github/blob/main/java.md#3-%EB%82%B4%EB%B6%80-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%99%80-%EC%9D%B5%EB%AA%85-%ED%81%B4%EB%9E%98%EC%8A%A4)

## 1. 다형성
#### 1. 다형성(polymorphism)이란?
   1. 부모-자식 상속 관계에 있는 클래스에서 상위클래스가 동일한 메세지로 하위 클래스들을 서로 다르게 동작시키는 객체 지향 원리
   2. 부모 클래스가 자식 클래스의 동작 방식을 알수 없어도 오버라이딩을 통해 자식 클래스에 접근할 수 있다.
   3. 동적바인딩 덕분에 부모가 자식이 어떤 일을 하는 지 몰라도, 자식 멤버 함수를 호출시킬 수 있다.
        1. 동적 바인딩 : 실행 시간 (Runtime) 즉, 파일을 실행하는 시점에 성격이 결정된다. 실제 참조하는 객체의 메소드를 호출한다. 
#### 2. 다형성의 장점
   1. 여러 객체를 하나의 타입으로 관리가 가능하기 때문에 코드 관리가 편리해 유지보수가 쉽다.
   2. 다형성을 활용하면 객체를 재사용하기 쉬워지기 때문에 코드 재사용성이 높아집니다.
   3. 클래스간의 의존성이 줄어들어 확장성이 높고 결합도가 낮아져 안전성이 높아집니다.
#### 3. 다형성 필수 조건
   1. 클래스 상속이 이루어져야됨
   2. 오버라이딩 필수
   3. 부모 타입으로 자식 클래스를 업캐스팅하여 객체를 생성해야 합니다.
#### 4. 다형성 구현 방법
   1. 상속 클래스 구현
   2. 메소드 오버라이딩
   3. 업캐스팅하여 객체 선언
   4. 부모 클래스 객체로 자식 메소드 호출

## 2. 동일성 vs 동등성이 무엇인가?
#### 1. 동일성(identity)
   1. 두 객체가 완전히 같은 경우를 의미한다.
   2. 사실상 하나의 객체로 봐도 무방하다.
   3. 주소 값이 같기에 두 변수가 같은 객체를 가리키게 된다.
   4. ==
#### 2. 동등성(equality)
   1. 두 개의 객체가 같은 정보를 갖고 있는 경우를 의미한다.
   2. 변수가 참조하고 있는 객체의 주소가 서로 다르더라도 내용만 같으면 두변수는 동등하다고 이야기할 수 있다.
    

## 3. equals, hashCode에 대해서
### 1. equals, hashCode가 왜 중요한가?
 #### 1. equals() 메소드 란?
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
  #### 2. hashCode()란?
   1. hashCode()는 객체의 hashCode를 리턴한다.
   2. hashCode는 일반적으로 각 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값
### 2. equals와 hashCode는 동시에 오버라이드 되어야한다. 
   1. 동일한 객체는 동일한 메모리 주소를 갖는다는 것을 의미 하므로, 동일한 객체는 동일한 해시코드를 가져야한다.
### 3. equals와 hashCode의 관계
   1. Java 프로그램을 실행하는 동안 equals에 사용된 정보가 수정되지 앟았다면, hashCode는 항상 동일한 정수값을 반환해야한다.(프로그램을 실행할 때 마다 달라지는 것은 상관이 없다.)
   2. 두 객체가 equals()에 의해 동일하다면, 두 객체의 hashCode() 값도 일치해야 한다.
   3. 두 객체가 equals()에 의해 동일하지 않다면 두 객체의 hashCode()값은 일치하지 않아도 된다.
### 4. 중요한 이유
   1. 같은 값인지 비교하기 위해서 중요하다.
### 5. equals, hashCode의 차이점
   1. equals는 비교하는 것이고 hashCode는 고유한 숫자를 나타내는 것이다.
### 6. 구현하는 방법
   1. Object에 명시되어있기 때문에 그냥 사용하거나 overriding해서 사용한다.

## 4. enum 클래스의 메모리 구조
### 1. enum과 메모리 구조
   1. 열거 상수는 상수 각각을 내부적으로 public static final 필드 이면서 객체로 제공되도록 합니다.
   2. static이 붙어있기 때문에 각각의 상수는 클래스 변수로 클래스 로더가 로드 시점에 JVM Method 영역에 해당 클래스 변수들을 항상 상주시켜 프로그램이 종료되기 전에는 언제든 가져다 쓸 수 있는 주소 공간을 확보합니다.
    ![메소드 영역 이미지](https://honbabzone.com/assets/images/post/java/emum-memory.png)

## 5. 예외
### 1. 예외 Exception
   - 예상한, 예상치 못한 일이 발생하는 것을 미리 예견하고 안전장치를 하는 것
### 2. try-catch

```java
 try{
   //예외가 발생하는 문장
} catch(예외의_종류_클래스 매개변수){
   //예외가 발생했을 때 처리
 } finally {
   //어떤 경우에도 반드시 실행됨
 }
```

1. try 안에서 예외가 발생하면 그 이하의 문장은 실행되지 않고 바로 catch 블록으로 넘어간다.
2. try에서 예외 발생하지 않으면 catch코드를 실행하지 않음
3. try블록 내에서 선언한 변수를 catch에서 사용 불가
4. try 1개, catch 여러개여도 된다.
5. 모든 예외의 부모클래스는 java.lang.Exception
6. catch의 매개 변수 클래스를 Exception로 둘 때는 맨 마지막 catch에 넣기(예상치 못한 예외 처리하기위한 용도로써 Exception클래스 없을 때 catch에서 오류를 잡지 못하면 컴파일 에러남.)

### 3. 예외의 종류는 3가지
   1. checked exception
   2. error
   3. runtime exception 혹은 unchecked exception
   - error와 unchecked exception을 제외한 모든 예외는 checked exception이다.
     #### 1. error
     - 에러는 자바프로그램 밖에서 발생한 예외
     - ex)서버 디스크 고장
     - 오류 이름이 Error로 끝나면 error, Exception으로 끝나면 예외
     - 더 큰 차이는 프로그램이 멈추느냐 계속 실행할 수 있느냐
     - Error는 프로세스에 영향을 주고 Exception은 쓰레드에만 영향을 준다.
     #### 2. runtime exception
     - 런타임 예외는 예외가 발생한 것을 미리 감지하지 못했을 때 발생
     - 런타임 예외에 해당하는 모든 예외들은 Runtime Exception을 확장한 예외
     - ex) NullPointerException
     - 이 예외를 catch에 넣지 않는다고 해서 컴파일할 때 예외가 발생하지 않는다. 하지만 실행시에는 발생할 가능성이 있다.
     - 컴파일시 체크하지 않기 때문에 unchecked exception이라고도 부름
     
### 4. java.lang.Throwable
 1. exception과 error의 공통 부모 클래스는 object, throwable클래스이다.
 2. throwable 클래스를 상속 받아 처리하도록 되어있는 이유는 exception, error 성격은 다르지만, 모두 동일한 이름의 메소드를 사용하여 처리하기위함. 
 
### 5. Throwable의 생성자
 1. Throwable()
 2. Throwable(String message)
        - 예외 메세지를 string으로 넘겨줌
 3. Throwable(String message, Throwable cause)
 4. Throwable(Throwable cause)
        - 예외의 원인을 Throwable 객체로 넘겨줄 수 있다.
### 6. Throwable 클래스에 선언되어 있고, Exception 클래스에서 Overriding한 메소드
 1. getMessage()
    1. 예외 메세지를 String 형태로 제공 받는다.
    2. 예외가 출력되었을 때 어떤 예외가 발생되었는지 확인할때 유용하다.
    3. 그 메세지를 활용하여 별도의 예외 메세지를 사용자에게 보여주려고 할 때 좋다.
 2. toString()
    1. 예외메세지를 string형태로 제공 받는다.
    2. getMessage() 보다 자세히, 예외 클래스 이름도 같이 제공한다.
 3. printStackTrace()
    1. 가장 첫 줄에는 예외 메세지 출력, 두번째줄 부터는 예외가 발생하게된 메소드들의 stack trace를 출력해줌. 
    2. 개발할 때만 사용하자. 시스템에 사용하면 많은 양의 로그가 쌓일 것이다.
            
### 7. throw와 throws
#### 1. throw
  1. 예외 클래스의 객체 생성을 하려면 try 블록 내에서 throw라고 명시한 후 new를 이용해서 객체를 생성하면 된다.
  2. 코드
     ```java
      if(number>12){
         throw new Exception("예외 메세지");
         }
     ```
  3. throw한 문장 이후에 있는 모든 try블록 내의 문장들은 수행 되지 않고, catch 블록으로 이동한다.  
  4. catch 블록 중에 throw한 예외와 동일하거나 상속 관계에 있는 예외가 있다면 그 블록에서 예외를 처리할 수 있다.
#### 2. throws
  1. 해당하는 예외가 없다면 발생된 예외는 메소드 밖으로 던져버린다. 즉, 예외가 발생된 메소드를 호출한 메소드로 던진다는 의미이다. 이럴 떄 사용하는 것이 throws 구문이다.
  2. 코드
     ```java
     public void throwsException(int number) throws Exception {
        if(number>12){
           throw new Exception("Number is over than 12");
        }
        System.out.println("Number is "+number);
     }
     ```
   3. 메소드에 선언해놓으면 예외가 발생했을 때 try-catch로 묶어주지 않아도 그 메소드를 호출한 메소드로 예외 처리를 위임하는 것이기 때문에 문제가 되지 않는다.
   4. throws로 메소드를 선언하면 개발이 어려워진다. 왜냐하면, throwsException을 호출한 메소드에서는 반드시 try-catch를 사용하거나 호출한 메소드를 throws 해주어야 한다. 후자는 좋은 습관이 아님
   5. 메소드에서 두 가지 이상의 예외를 던질 수 있다면 콤마로 구분하여 예외클래스 이름을 적어주면 된다.
   6. catch 블록에서 예외를 throw할 경우에도 메소드 선언의 throws 구문에 해당 예외가 정의되어 있어야만 한다.
   7. 예외를 throw하는 이유는 해당 메소드에서 예외를 처리하지 못하는 상황이거나, 미처 처리하지 못한 예외가 있을 경우에 대비하기 위함이다.

### 8. 예외 만들기
   1. Exception을 처리하는 예외 클래스는 개발자가 임의로 추가해서 만들 수 있다.
   2. 조건
   : Throwable이나 그 자식 클래스의 상속을 받아야 한다.
   : 하지만 Exception을 처리하는 클래스라면 java.lang.Exception 클래스의 상속을 받는 것이 좋다. 
   3. 내가 만든 예외 클래스 코드
   ```java
   public class MyException extends Exception {
      public MyException(){
         super();
      }
      public MyException(String message){
         super(message);
      }
   }
   ```
   4. 내가 만든 예외 클래스 코드를 사용하는 클래스
   ```java
   public class CustomException {
      public static void main(String args[]){
         CustomException sample = new CustomException();
         try{
            sample.throwMyException(13);
         } catch(MyException mye) {
            mye.printStackTrace();
         }
      }
      public void throwMyException(int number) throws MyException{
         try {
            if(number>12){
               throw new MyException("Number is over than 12");
            }
         } catch (MyException e){
            e.printStackTrace();
         }
      }
   }
   ```
   5. 코드 해석
      1. 직접 만든 예외를 던지고, catch 블록에서 사용하면 된다.
      2. throwMyException 메소드를 호출하는 메소드에서(여기서는 main() 메소드) 반드시 MyException으로 catch할 필요는 없다. MyException의 부모클래스인 Exception클래스로 catch해도 무방하다.

### 9. 자바 예외 처리 전략
   1. 자바에 예외를 처리할 때에는 표준을 정해 두어야만 한다.
   2. 예
      1. 나만의 예외 클래스를 만들 때 예외가 항상 발생하지 않고, 실행시에 발생할 확률이 매우 높은 경우에는 런타임 예외로 만드는 것이 나을 수도 있다. 
      2. 이렇게 되면 해당 예외를 던지는 메소드를 사용하더라도 try-catch로 묶지 않아도 컴파일시에 예외가 발생하지 않는다.
      3. 하지만, 이런 경우에는 예외가 발생할 경우 해당 클래스를 호출하는 다른 클래스에서 예외를 처리하도록 구조적인 안전 장치가 되어 있어야만 한다.
      4. 안전 장치라고 하는 것은 try-catch로 묶지 않은 메소드를 호출하는 메소드에서 예외를 처리하는 try-catch가 되어 잇는 것을 이야기한다.
   3. '자바 예외 전략'이나 'Java Exception Strategy'로 구글에 검색하면 많은 자료를 찾을 수 있다.

## 6. String
### 1. String 클래스 선언부
  1. 코드
   ```java
   public final class String extends Object implements Serializable, Comparable<String>, CharSequence
   ```
  2. **Serializable**
  - 인터페이스를 implements 한 클래스는 선언되어 있는 메소드의 몸통을 구현해야만 한다. 하지만 Serializable 인터페이스는 구현해야 하는 메소드가 하나도 없는 인터페이스다.
  - Serializable 인터페이스를 구현한다고 선언해 놓으면 해당 객체를 파일로 저장하거나 다른 서버에 전송 가능한 상태가 된다.
  3. **Comparable<String>**
  - 이 인터페이스는 compareTo()라는 메소드 하나만 선언되어 있다.
  - compareTo() 메소드는 매개 변수로 넘어가는 객체와 현재 객체가 같은지를 비교하는 데 사용된다.
  - equals() 메소드와 다른 점은 compareTo() 메소드의 리턴 타입은 int다.
  - compareTo() 메소드는 같으면 0이지만 순서 상으로 앞에 있으면 -1, 뒤에 있으면 1을 리턴한다. 객체의 순서를 처리할 때 유용하다.
  - <String>은 generic이다. generic은 클래스나 메소드에서 사용할 내부 데이터 타입을 컴파일 시에 미리 지정하는 방법
  4. **CharSequence**
  - 이 인터페이스는 해당 클래스가 문자열을 다루기 위한 클래스라는 것을 명시적으로 나타내는 데 사용된다.
### 2. String 생성자
   1. 용어
      1. **Character Set(캐릭터 셋)**
      - 문자의 집합을 의미하며, 특정 나라의 글자를 말한다.
      2. **Decoding(디코딩)**
      - 일반적으로 암호화되어 있거나 컴퓨터가 이해할 수 있는 값들을 알아보기 쉽게 변환하는 것을 말한다.
   2. String 클래스의 생성자
      1. **String()**
      - 비어있는 String 객체를 생성한다.
      - String name = null;
      - 위의 코드가 더 효율적이다.
      2. **String(byte[] bytes)**
      - 현재 사용중인 플랫폼의 캐릭터 셋을 사용하여 제공된 byte배열을 디코딩한 String 객체를 생성한다.
      3. **String(byte[] bytes, Charset charset)**
      - 지정된 캐릭터 셋을 사용하여 제공된 byte 배열을 디코딩한 String 객체를 생성한다.
      4. **String(byte[] bytes, String charsetName)**
      - 지정한 이름을 같는 캐릭터 셋을 사용하여 지정한 byte 배열을 디코딩한 String 객체를 생성한다.
      5. **String(byte[] bytes, int offset, int length)**
      - 현재 사용중인 플랫폼의 기본 캐릭터 셋을 사용하여 지정한 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      6. **String(byte[] bytes, int offset, int length, Charset charset)**
      - 지정된 캐릭터 셋을 사용하여 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      7. **String(byte[] bytes, int offset, int length, String charsetName)**
      - 지정한 이름을 갖는 캐릭터 셋을 사용하여 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      8. **String(char[] value)**
      - char 배열의 내용들을 붙여 String 객체를 생성한다.
      9. **String(char[] value, int offset, int count)**
      - char 배열의 일부 내용들을 붙여 String 객체를 생성한다.
      10. **String(int[] codePoints, int offset, int count)**
      - 유니코드 코드 위치(Unicode code point)로 구성되어 있는 배열의 일부를 새로운 String 객체를 생성한다.
      11. **String(String original)**
      - 매개 변수로 넘어온 String과 동일한 값을 갖는 String 객체를 생성한다. 복제본을 생성한다.
      12. **String(StringBuffer buffer)**
      - 매개 변수로 넘어온 StringBuffer 클래스에 정의 되어 있는 문자열의 값과 동일한 String 객체를 생성한다.
      13. **String(StringBuilder builder)**
      - 매개 변수로 넘어온 StringBuilder 클래스에 정의되어 잇는 문자열의 값과 동일한 String 객체를 생성한다.
   3. getBytes()
      1. 생성자의 매개 변수로 받는 byte배열을 생성하는 방법이다.
      2. getBytes()
         1. **getBytes(**
            1. 리턴 타입 : byte[]
            2. 기본 캐릭터 셋의 바이트 배열을 생성한다.
            3. 같은 프로그램 내에서 문자열을 byte배열로 만들 때 사용
         2. **getBytes(Charset charset)**
            1. 리턴 타입 : byte[]
            2. 지정한 캐릭터 셋 객체 타입으로 바이트 배열을 생성한다.
            3. 다른 시스템에서 전달 받은 문자열을 byte 배열로 변환 할때 사용. 서로 다른 캐릭터 셋을 사용할 수 있기 때문이다.
         3. **getBytes(String charsetName)**
            1. 리턴 타입 : byte[]
            2. 지정한 이름의 캐릭터 셋을 갖는 바이트 배열을 생성한다.
            3. 다른 시스템에서 전달 받은 문자열을 byte 배열로 변환 할때 사용. 서로 다른 캐릭터 셋을 사용할 수 있기 때문이다.
      3. 코드

      ```java
      public class StringSample {

	  public static void main(String[] args) {
		StringSample sample = new StringSample();
		sample.convert();
	   }
	   public void convert() {
		try {
		String korean = "한글 ";
		
		byte[] array1=korean.getBytes();
		for(byte data:array1) {
			System.out.println(data + " ");
		}
		System.out.println();
		String korean2=new String(array1);
		System.out.println(korean2);
		}catch (Exception e) {
			e.printStackTrace();
		}
	   }
      }

      ```
      1. '한글'이라는 값을 갖는 String 객체인 korean을 생성했다.
      2. getByte() 메소드를 사용하여 korean을 byte 배열로 만들었다.
      3. 만들어진 byte 배열에 어떤 값들이 있는지 보기 위해서 for루프를 사용하여 각각의 byte값을 출력하도록 해놓았다.
      4. byte 배열을 갖고 String 객체를 만들기 위해서 byte 배열(array1)을 매개 변수로 갖는 String 객체를 생성하고, 그 문자열을 출력했다.
      5. try-catch로 감싼 이유 
         1. 캐릭터 셋을 지정하는 메소드 및 생성자들 때문이다.
         2. byte 배열과 String 타입의 캐릭터 셋을 받는 생성자와 getBytes() 메소드 중에서 String 타입의 캐릭터 셋을 받는 메소드
         3. 2번의 생성자와 메소드는  UnsupportedEncodingException을 발생시킬 수있다. 존재하지 않는 캐릭터 셋의 이름을 지정할 경우에는 이 예외가 발생하게 됨.

### 3. null check
   1. 모든 객체를 처리할 때에는 널 체크를 반드시 해야한다.
   2. 객체가 null 이라는 것은 객체가 아무런 초기화도 되어있지 않으며, 클래스에 선언되어있는 어떤 메소드도 사용할 수 없다.

### 4. String의 메소드
   1. length()
      1. 리턴 타입 : int
      2. 문자열의 길이를 리턴한다.
      3. 배열은 메소드가 없는 특수한 객체이다. 배열은 괄호가 없는 length를 사용하고 배열을 제외한 클래스의 String 객체의 길이를 확인하기 위해서는 length()라는 메소드를 사용해야한다.
      4. 공백도 길이에 포함됨
      ```java
      System.out.println(text.length);
      ```
   2. isEmpty()
      1. 리턴 타입 : boolean
      2. 문자열이 비어 있는지를 확인한다. 
      3. 비어있으면 true를 리턴한다.
      ```java
      System.out.println(text.isEmpty());
      ```
   3. 문자열이 같은지 비교하는 메소드
      - boolean : equals(Object anObject)
      - boolean : equalsIgnoreCase(String anotherStr)
      - int : compareTo(String anotherStr)
      - int : compareToIgnoreCase(String str)
      - boolean : contentEquals(CharSequence cs)
      - boolean : contentEquals(StringBuffer sb)
         1. IgnoreCase가 붙은 메소드들은 대소문자 구분을 할지 안할지 여부가 다름
         2. equals() 메소드
         ```java
         public void checkCompare(){
            String text = "Check value";
            String text2 = "Check value";
            String text3 = "check value";
            if(text==text2){
               System.out.println("text==text2 result is same.");
            } else {
               System.out.println("text==text2 result is different")
            }
            if(text.equals("Check value")){
               System.out.println("text.equals(text2) result is same.");
            }
            if(text.equalsIgnoreCase(text3)){
               System.out.println("text.equalsIgnoreCase(text3) result is same.");
            }
            }
         ```
         - text==text2가 성립하는 이유는 자바에서 객체들을 재사용하기 위해 Constant Pool이라는 것이 존재하기 때문이다. 
         -  String의 경우 동일한 값을 갖는 객체가 있으면 이미 만든 객체를 재사용한다.
         3. compareTo()
         - 보통 정렬(sorting)할 때 사용한다.
         - true, false의 결과가 아니라 비교하려는 매개 변수로 넘겨준 String 객체가 알파벳 순으로 앞에 있으면 양수를 뒤에 있으면 음수를 리턴한다. 알파벳 순서만큼 그 숫자 값은 커진다.
         - 
         ```java
         public void checkCompareTo(){
            String text = "a";
            String text2 = "b";
            String text3 = "c";

            System.out.println(text2.compareTo(text));//1
            System.out.println(text2.compareTo(text3));//-1
            System.out.println(text.compareTo(text3));//-2
         }
         ```
         4. contentEquals(CharSequence cs), contentEquals(StringBuffer sb)
         - contentEquals() 메소드는 매개 변수로 넘어오는 CharSequence와 StringBuffer객체가 String 객체와 같은지를 비교하는 데 사용된다.
   4. 특정 조건에 맞는 문자열이 있는지를 확인하는 메소드
      - boolean : startsWith(String prefix)
      - boolean : startsWith(String prefix, int toffset)
      - boolean : endWith(String suffix)
      - boolean : contains(CharSequence s)
      - boolean : matches(String regex)
      - boolean : regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len)
      - boolean : regionMatches(int toffset, String other, int ooffset, int len)
         1. startsWith()
            1. 매개변수로 넘겨준 값으로 시작하는지를 확인한다.
         2. indexOf()
            1. 매개 변수로 넘겨준 값이 있는지 확인
            2. 단점은 문자열의 모든 내용을 확인해 봐야 한다.
         3. endWith()
            1. 매개 변수로 넘어온 값으로 해당 문자열이 끝나는지 확인
         4. 코드
         ```java
         public class StringCheck{
            public static void main(String args[]){
               StringCheck sample = new StringCheck();

               String addresses[]=new String[]{
                  "서울시 구로구 신도림동",
                  "경기도 성남시 분당구 정자동 개발 공장",
                  "서울시 구로구 개봉동",
               };
               sample.checkAddress(addresses);
            }
            public void checkAddress(String[] addresses){
               int startCount=0,endCount=0;
               String startText="서울시";
               String endText = "동";
               for(String adress:addresses){
                  if(address.startWith(startText)){
                     startCount++
                  }
                  if(address.endsWith(endText)){
                     endCount++;
                  }
               }
               System.out.println("Starts with "+ startText+" count is "+ startCount);
               System.out.println("Ends with "+endText+" count is "+endCount);
            }
         }
         ```
         - 실행 결과
         - Starts with 서울시 count is 2
         - Ends with 동 count is 2

         5. contains(CharSequence s)
            1. 매개변수로 넘어온 값이 문자열에 존재하는지를 확인한다.
         6. matches(String regex)
            1. contains()와 비슷하지만 매개 변수로 넘어오는 값이 '정규 표현식(Regular Expression)'으로 되어 있어야 한다.
            2. 정규 표현식
               - 이메일을 점검하거나, 웹 페이지에 있는 URL을 점검하는 등의 작업을 쉽게 하기 위해서 공식에 따라 만든 식
         7. regionMatches()
            - regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len)
            - regionMatches(int toffset, String other, int ooffset, int len)

            1. 문자열 중에서 특정 영역이 매개 변수로 넘어온 문자열과 동일한지를 확인하는 데 사용한다.
            2. 매개 변수
               1. ignoreCase : true일 경우 대소문자 구분을 하지 않고, 값을 비교한다.
               2. toffset : 비교 대상 문자열의 확인 시작 위치를 지정한다.
               3. other : 존재하는지를 확인할 문자열을 의미한다.
               4. oofset : other 객체의 확인 시작 위치를 지정한다.
               5. len : 비교할 char의 개수를 지정한다.
            3. 매개 변수 중에서 값이 다음과 같은 경우에는 결과가 무조건 false로 나온다.
               1. toffset이 음수일 때
               2. ooffset이 음수일 때
               3. toffset+len이 비교 대상으 길이보다 클 떄
               4. ooffset+len이 other 객체의 길이보다 클 떄
               5. ignoreCase가 false인 경우에는 비교 범위의 문자들 중 같은 위치(index)에 있는 char가 다를 때
               6. ignoreCase가 true인 경우에는 비교 범위의 문자들을 모두 소문자로 변경한 후 같은 위치(index)에 있는 char가 달라야 한다.
            4. 코드
            ```java
            public void checkMatch() {
               String text = "This is a text";
               String compare1 = "is";
               String compare2 = "this";
               System.out.println(text.regionMatches(2, compare1, 0, 1)); //true
               System.out.println(text.regionMatches(5, compare1, 0, 2)); //true
               System.out.println(text.regionMatches(true,0 ,compare2, 0, 4)); // true
            }
            ```
            5. 각 char의 위치

            |T|h|i|s| |i|s| |a| |t|e|x|t|
            |-|-|-|-|-|-|-|-|-|-|-|-|-|-|
            |0|1|2|3|4|5|6|7|8|9|10|11|12|13|

   5. String내에서 위치를 찾아내는 방법
      - int : indexOf(int ch)
      - int : indexOf(int ch, int fromIndex)
      - int : indexOf(String str)
      - int : indexOf(String str, int fromIndex)
      - int : lastIndexOf(int ch)
      - int : lastIndexOf(int ch, int fromIndex)
      - int : lastIndexOf(String str)
      - int : lastIndexOf(String str, int fromIndex)
         1. indexOf()
            1. 앞에서 부터(가장 왼쪽부터) 문자열이나 char를 찾는다.
            2. 코드
            ```java
            public void checkIndexOf(){
               String text="Java technology is both a programming language and a platform.";
               System.out.println(text.indexOf('a')); //1
               System.out.println(text.indexOf("a ")); //3
               System.out.println(text.indexOf('a',20)); //24
               System.out.println(text.indexOf("a ",20)); //24
               System.out.println(text.indexOf('z')); //-1
            }
            ```
               - char은 정수형이기 때문에 int 값으로 자동 형변환이 일어난다.
               - fromIndex : fromIndex의 자리 부터 값을 확인한다.  
               - z는 문장에 없으므로 -1을 출력하였다.
         2. lastIndexOf()
            1. 뒤에서부터(가장 오른쪽) 찾는다.
   6. String의 값의 일부를 추출하기 위한 메소드
      1. char 단위의 값을 추출하는 메소드
         1. **charAt(int index)**
            1. 리턴 타입 : char
            2. 특정 위치의 char 값을 리턴한다.
         2. **getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)**
            1. 리턴 타입 : void
            2. 매개 변수로 넘어온 dst라는 char 배열 내에 srcBegin에서 srcEnd에 있는 char를 저장한다. 
            3. dst 배열의 시작위치는 dstBegin이다.
         3. **codePointAt(int index)**
            1. 리턴 타입 : int
            2. 특정 위치의 유니코드 값을 리턴한다.
            3. 리턴 타입은 int지만, 이 값을 char로 형 변환하면 char 값을 출력할 수 있다.
         4. **codePointBefore(int index)**
            1. 리턴 타입 : int
            2. 특정 위치 앞에 있는 char의 유니코드 값을 리턴한다.
            3. 리턴 타입은 int지만, 이 값을 char로 형 변환하면 char 값을 출력할 수 있다.
         5. **codePointCount(int beginIndex, int endIndex)**
            1. 리턴 타입 : int
            2. 지정한 범위에 있는 유니코드 개수를 리턴한다.
         6. **offsetByCodePoints(int index, int codePointOffset)**
            1. 리턴 타입 : int
            2. 지정된 index부터 오프셋이 설정된 인덱스를 리턴한다.
            3. 문자열 인코딩과 관련된 문제를 해결하기 위해서 사용된다.
      2. char 배열의 값을 String으로 변환하는 메소드
         1. **copyValueOf(char[] data)**
            1. 리턴 타입 : static String
            2. char 배열에 있는 값을 문자열로 변환한다.
         2. **copyValueOf(char[] data, int offset, int count)**
            1. 리턴 타입 : static String
            2. char 배열에 있느 값을 문자열로 변환한다.
            3. 단 offset위치부터 count까지의 개수만큼만 문자열로 변환한다.
            4. 코드
            ```java
            char value[] = new char[]{'J','a','v','a'};
            String javaText = String.copyValueOf(values);
            ```
      3. String의 값을 char 배열로 변환하는 메소드
         1. **toCharArray()**
            1. 리턴 타입 : char[]
            2. 문자열을 char 배열로 변환하는 메소드
      4. 문자열의 일부 값을 잘라내는 메소드
         1. **substring(int beginIndex)**
            1. 리턴 타입 : String
            2. beginIndex부터 끝까지 대상 문자열을 잘라 String으로 리턴한다.
            3. 코드
            ```java
            public void checkSubstring(){
               String text = "Java technology";
               String technology = text.substring(5);
               System.out.println(technology); //technology
            }
            ```
         2. **substring(int beginIndex, int endIndex)**
            1. 리턴 타입 : String
            2. beginIndex부터 endIndex까지 대상 문자열을 잘라 String으로 리턴한다.
         3. **subSequence(int beginIndex, int endIndex)**
            1. 리턴 타입 : CharSequence
            2. beginIndex부터 endIndex까지 대상 문자열을 잘라 CharSequence 타입으로 리턴한다.
      5. 문자열을 여러 개의 String 배열로 나누는 split 메소드
         1. **split(String regex)**
            1. 리턴 타입 : String[]
            2. regex에 있는 정규 표현식에 맞추어 문자열을 잘라 String의 배열로 리턴한다.
         2. **split(String regex, int limit)**
            1. 리턴 타입 : String[]
            2. regex에 있는 정규 표현식에 맞추어 문자열을 잘라 String의 배열로 리턴한다. 
            3. 이때 String 배열의 크기는 limit 보다 커서는 안 된다.
         3. **java.util.StringTokenizer**
            1. 문자열을 여러 개의 문자열의 배열로 나누는 방법
            2. 정규 표현식을 사용하여 문자열을 나누려고 한다면 String클래스의 split()메소드를 사용하면 되고 그냥 특정 String으로 문자열을 나누려고 한다면 StringTokenizer 클래스를 사용 하는 것이 편하다.
   7. String 값을 바꾸는 메소드
      1. 문자열을 합치는 메소드와 공백을 없애는 메소드
         1. **concat(String str)**
            1. 리턴 타입 : String
            2. 매개 변수로 받은 str을 기존 문자열의 우측에 붙인 새로운 문자열 객체를 생성하여 리턴한다.
            3. concat() 메소드를 사용하여 문자열을 더할 일이 있다면, StringBuffer나 StringBuilder 클래스를 사용하여 문자열을 더하는 것이 좋다.
         2. **trim()**
            1. 리턴 타입 : String
            2. 문자열의 맨 앞과 맨 뒤에 있는 공백들을 제거한 문자열 객체를 리턴한다.
            3. 작업하려는 문자열이 공백만으로 이루어진 값인지, 공백을 제외한 값이 있는지 확인하기 편리하다.
            4. 코드
            ```java
            String text = " a ";
            if(text!= null && text.trim().length()>0){
               System.out.println("OK");
            }
            ```
            5. null 체크를 하지 않으면, 값이 null인 객체의 메소드를 호출하면 NullPointerException이 발생한다. String을 조작하기 전에는 null 체크하는 습관을 갖자.
      2. 내용을 교체하는 메소드
         1. **replace(char oldChar, char newChar)**
            1. 리턴 타입 : String
            2. 해당 문자열에 있는 oldChar의 값을 newChar로 대치한다.
         2. **replace(CharSequence target, CharSequence replacement)**
            1. 리턴 타입 : String
            2. 해당 문자열에 있는 target과 같은 값을 replacement로 대치한다.
         3. **replaceAll(String regex, String replacement)**
            1. 리턴 타입 : String
            2. 해당 문자열의 내용중 regex에 표현된 정규 표현식에 포함되는 모든 내용을 replacement로 대치한다.
         4. **replaceFirst(String regex, String replacement)**
            1. 리턴 타입 : String
            2. 해당 문자열의 내용 중 regex에 표현된 정규 표현식에 포함되는 첫번째 내용을 replacement로 대치한다.
         5. **문자열에 있는 내용 중 일부를 변경하는 작업을 수행한다.**
         6. **이 메소드를 수행해도 기존 문자열의 값은 바뀌지 않는다.**

      3. 특정 형식에 맞춰 값을 치환하는 메소드
         1. **format(String format, Object... args)**
            1. 리턴 타입 : static String
            2. format에 있는 문자열의 내용 중 변환해야 하는 부분을 args의 내용으로 변경한다.
         2. **format(Locale l, String format, Object... args)**
            1. 리턴 타입 : static String
            2. format에 있는 문자열의 내용 중 변환해야 하는 부분을 args의 내용으로 변경한다. 단 첫 매개 변수인 Locale 타입의 l에 선언된 지역에 맞추어 출력한다.
            2. Locale은 지역적으로 다른 표현 형식을 제공하기 위한 것이다.보통 Locale을 지정하지 않으면 기본적으로 자바 프로그램이 수행되는 OS의 지역 정보를 기본으로 따른다.
         3. **정해진 기준에 맞춘 문자열이 있으면, 그 기준에 있는 내용을 변환한다. 자바에서는 %d는 정수형을, %s는 String을, %f는 소수점이 있는 숫자, %%는 %를 의미한다.**
         4. **코드**
         ```java
         public void checkFormat(){
            String text="제 이름은 %s입니다. 지금까지 %d 권의 책을 썻고, " +"gkfndp %f %%의 시간을 책을 쓰는데 할애하고 있습니다."
            String realText=String.format(text, "이상민",7,10.5);
            System.out.println(realText);
         } 
         ```
      4. 대소문자를 바꾸는 메소드
         1. **toLowerCase()**
            1. 리턴 타입 : String
            2. 모든 문자열의 내용을 소문자로 변경한다.
         2. **toLowerCase(Locale locale)**
            1. 리턴 타입 : String
            2. 지정한 지역 정보에 맞추어 모든 문자열의 내용을 소문자로 변경한다.
         3. **toUpperCase()**
            1. 리턴 타입 : String
            2. 모든 문자열의 내용을 대문자로 변경한다.
         4. **toUpperCase(Locale locale)**
            1. 리턴 타입 : String
            2. 지정한 지역 정보에 맞추어 모든 문자열의 내용을 대문자로 변경한다.
      5. 기본 자료형을 문자열로 변환하는 메소드
         - static String : valueOf(boolean b)
         - static String : valueOf(char c)
         - static String : valueOf(char[] data)
         - static String : valueOf(char[] data, int offset, int count)
         - static String : valueOf(double d)
         - static String : valueOf(float f)
         - static String : valueOf(int i)
         - static String : valueOf(long l)
         - static String : valueOf(Object obj)
         ```java
         byte b = 1;
         String byte1 = String.valueOf(b);
         String byte2 = b + "";
         ```
         1. 대부분 기본 자료형을 String 타입으로 변환할 필요가 있을 때에는 String과 합치는 과정을 거친다. 그럴 경우에는 valueOf() 메소드를 사용할 필요가 없다. 하지만 String으로 변환만 해놓고 별도의 문자열과 합치는 과정이 없을 경우에는 valueOf()메소드를 사용하는 것을 권장한다.
         2. valueOf 메소드의 매개 변수로 객체가 넘어왔을 경우는 주의 해야한다. toString을 구현한 객체나, 정상적인 객체를 valueOf()메소드에 넘겨주면 toString()의 결과를 리턴해준다.
         3. 하지만 null의 객체인 경우에는 이야기가 달라진다. null인 객체는 toString() 메소드를 사용할 수 없다. NullPointerException이 발생한다. 
         4. 그러한 결과를 방지하기 위해서 객체를 출력할 때 valueOf()메소드를 사용하면 좋다. valueOf()메소드는 객체가 null이면 "null"이라는 문자열을 리턴해주기 때문이다. 만약 null이 아니면, toString() 메소드를 호출한 결과가 리턴된다.
         5. System.out.println()나 System.out.print() 메소드에서 null인 객체를 출력했을 때 NullPointerException이 발생하지 않는 이유도 이 떄문이다.
      
   8. 절대 사용하면 안 되는 intern()메소드가 있다.
         1. 자바가 아닌 c로 구현되어 있는 native 프로그래밍 언어로 작성한 메소드 중 하나다. native 메소드 이기 때문에 쓰지 말라는 것이 아니고, 시스템의 심각한 성능 저하를 발생 시킬 수 있다.
         2. 코드
         ```java
         public void internCheck(){
            String text1 = "Java Basic";
            String text2 = "Java Basic";
            String text3 = new String("Java Basic");
            text3 = text3.intern();
            System.out.println(text==text2); //true
            System.out.println(text1==text3); //true
            System.out.println(text1.equals(text3)); //true
         }
         ```
         - new String(String)으로 생성한 문자열 객체라고 할지라도, 풀에 해당 값이 있으면 풀에 있는 값을 참조하는 객체를 리턴한다.
         - 동일한 문자열이 없으면 풀에 값을 추가한다. 
         - intern()메소드를 사용한 후 equals()가 아닌 ==으로 동일한지 비교할 수 있다.
         - ==으로 비교하는 것이 훨씬 빠르다.
         - 새로운 문자열을 다수 만드는 프로그램에서 intern() 메소드로 문자열 풀에 값을 할당하도록 만들면 저장되는 영역은 한계가 있어 그 영역을 별도로 메모리를 청소한다.
         - 따라서 작은 연산 하나를 위해 전체 자바 시스템의 성능에 악영향을 준다.
         - 우리가 만드는 앱에서 생성하는 문자열이 정해져 있고, 그 문자열들만 intern()메소드를 호출하여 사용하면 사용 가능
         - 하지만 생성되는 문자열이 완전히 정해져 있는 시스템은 거의 없다.

### 5. StringBuffer와 StringBuilder
   1. String은 immutable(불변)한 객체다. 한 번 만들어지면 더 이상 그 값을 바꿀 수 없다.
   2. String 문자열을 더하면 새로운 String 객체가 생성되고, 기존의 객체는 버려진다. 하나의 String을 만들고 더하는 작업을 하면 계속 쓰레기를 만들게 된다. 이러한 단점을 보완하기 위해 StringBuffer와 StringBuilder가 생겼다.
   3. 두 클래스에서 제공하는 메소드는 동일하다.
   4. StringBuffer는 Thread safe 하고, StringBuilder는 Thread safe 하지 않다고 한다.
   5. 기능은 같지만 StringBuffer가 StringBuilder 보다 안전하다.
   6. 속도는 Thread safe 하지 않는 클래스가 더 빠르다.
   7. StringBuffer와 StringBuilder 클래스는 문자열을 더하더라도 새로운 객체를 생성하지 않는다.
   8. (+)를 사용하여 더할 수 없다. append()를 사용한다. 매개 변수로 모든 기본 자료형과 참조 자료형을 포함한다.

   ```java
   StringBuilder sb = new StringBuilder();
   sb.append("Hello");
   sb.append(" world");
   sb.append("Hello").append(" world"); 
   ```
   9. append()의 매개 변수가 정해진 문자열이라면 무쓸모 이지만 매개 변수가 항상 변하는 값(변수로 받은 값)이라면 유용하다.
   10. append()는 세미콜론이 나오기 전에 계속 붙여도 된다. append()를 수행한 후에는 해당 StringBuilder 객체가 리턴 되므로 그 객체에 계속 붙여도 무방하다.
   11. JDK 5 이상에서는 String의 더하기 연산을 할 경우, 컴파일할 때 자동으로 해당 연산을 StringBuilder로 변환해 준다. 하지만 for루프등 반복 연산을 할 때에는 자동으로 변환을 해주지 않는다.
   12. String과 StringBuilder, StringBuffer 클래스의 공통점의 첫번째는 모두 문자열을 다룬다는 점이다.
   13. 두번째는 CharSequence 인터페이스를 구현했다는 점이다. 세 가지 중 하나의 클래스를 사용하여 매개 변수를 받는 작업을 할 때 CharSequence 타입으로 받는 것이 좋다.
   14. 언제 StringBuilder를 사용하고, 언제 StringBuffer클래스를 사용할까? 
       1. 하나의 메소드 내에서 문자열을 생성하여 더할 경우에는 StringBuilder를 사용해도 전혀 상관없다.
       2. 어떤 클래스에서 문자열을 생성하여 더하기 위한 문자열을 처리하기 위한 인스턴스 변수가 선언되었고, 여러 쓰레드에서 이 변수를 동시에 접근하는 일이 있을 경우에는 StringBuffer를 사용해야한다.

## 7. Nested 클래스
### 1. Nested 클래스
   1. 클래스 안에 클래스가 들어간 형태.
   2. 존재 이유
      - 자바 기반의 UI 처리를 할 때 사용자의 입력이나, 외부의 이벤트에 대한 처리를 하는 곳의 코드를 간단하게 표현하기 위함.
      - Static Nested클래스를 사용하는 이유는 한 곳에서만 사용되는 클래스를 논리적으로 묶어서 처리할 필요가 있을 때
      - 내부 클래스를 사용하는 이유는 캡슐화가 필요할 때
      - 소스의 가독성과 유지보수성을 높이고 싶을 때

   3. Nested 클래스는 static으로 선언되었는지에 따라 "Static nested 클래스"와 "inner(내부) 클래스"로 구분된다.
   4. 내부 클래스는 두 가지로 나뉘는데 이름이 있는 내부 클래스는 "로컬(지역)내부클래스 local inner class", 이름이 없는 내부 클래스는 "익명 내부 클래스 anonymous inner class"라고 부른다. 

   ![내부클래스 이미지](https://compmath.korea.ac.kr/indust/_images/graphviz-2cb2987cf743035df2c1e58b0c128d9e94993d48.png)

### 2. Static nested 클래스의 특징
   1. 내부 클래스는 감싸고 있는 외부 클래스의 변수에 접근할 수있다.(private 가능) 하지만 Static nested 클래스를 그렇게 사용하는 것은 불가능하다.

   ```java
   public class OuterOfStatic {
      static class StaicNested {
         private int value=0;
         public int getValue(){
            return value;
         }
         public void setValue(int value){
            this.value = value;
         }
      }
   } 
   ```

   2. 코드 해석
      1. OuterOfStatic이라는 클래스를 선언했다.
      2. OuterOfStatic 내부에 static으로 선언된 StaticNested라는 클래스가 선언되어 있다. 그 안에 선언된 메소드의 내용들은 간단하게 인스턴스 변수의 값을 지정하고, 조회하는 작업을 수행한다.
      3. 내부에 있는 클래스는 별도로 컴파일할 필요가 없다. 감싸고 있는 클래스를 컴파일 하면 자동으로 컴파일되기 때문이다.
      4. 별도의 두 개의 클래스가 만들어진다. 
         - OuterOfStatic.class
         - OuterOfStatic$StaticNested.class
   
   3. StaticNested 클래스의 객체를 생성하는 방법
      1. 코드
      ```java
      public  class NestedSample{
         public static void main(String[] args){
            NestedSample sample = new NestedSample();
            sample.makeStaticNestedObject();
         }
         public void makeStaticNestedObject(){
            OuterOfStatic.StaticNested staticNested = new OuterOfStatic.StaticNested();
            staticNested.setValue(3);
            System.out.println(staticNested.getValue());
         }
      }
      ```
      2. 코드 해석
         1. 클래스 이름 뒤에 .을 찍고 Static Nested클래스 이름을 쓰면된다.
         2. 객체를 생성한 후엔 일반 클래스와 동일하게 사용한다.
         3. 겉으로 보기에는 유사하지만, 내부적 구현이 달라야 할 때 static nested클래스를 사용한다.

### 3. 내부 클래스와 익명 클래스
   1. 코드
   ```java
   public class OuterOfInner {
      class Inner {
         private int value = 0;
         public int getValue(){
            return value;
         }
         public void setValue(int value){
            this.value = value;
         }
      }
   }
   ```
   2. InnerSample 클래스의 코드
   ```java
   public class InnerSample {
      public static void main(String args[]){
         InnerSample sample = new InnerSample();
         sample.makeInnerObject();
      }
      public void makeInnerObject(){
         OuterOfInner outer = new OuterOfInner();
         OuterOfInner.Inner inner= outer.new Inner();
         inner.setValue(3);
         System.out.println(inner.getValue());
      }
   }
   ```
   3. 코드 해석
      1. 객체를 생성한 다음 사용하는 방법은 차이가 없다.
      2. 객체를 생성하는 방법에 차이가 있다. Inner 클래스를 감싸고 있는 OuterOfInner라는 클래스의 객체를 만들어야한다.
      3. 그 객체를(outer) 통해서 Inner 클래스의 객체를 만들 수 있다.
   4. Inner 클래스의 객체를 만드는 방법이 복잡한데도 만들어진 이유
      1. 캡슐화
         - 하나의 클래스에서 어떤 공통적인 작업을 수행하는 클래스가 필요한데 다른 클래스에서 그 클래스가 필요없을 때 사용한다.
      2. GUI(사용자 화면용 애플리케이션) 관련 프로그램을 개발할 때 가장 많이 사용한다.
         - GUI에서 내부 클래스들이 많이 사용되는 부분은 Listener라는 것을 처리할 때다. 
         - 사용자가 버튼을 클릭하거나, 키보드를 입력할 때에는 모두 Event라는 것이 발생한다.
         - 어떤 버튼이 눌렸을 때 수행해야하는 작업은 대부분 상이하다.버튼 마다 수행해야하는 작업을 정의하기 위해서 내부 클래스를 만들면 편하다. 내부 클래스 만드는 것 보다 쉬운 방법은 "익명 클래스"를 만드는 것이다.
   5. 익명 클래스 코드
         ```java
         package c.inner;

         public interface EventListener {
            public void onClick();
         }
         ```

         ```java
         package c.inner;

         public class MagicButton {
            public magicButton(){

            }
            private EventListener listener;
            public void setListener(EventListener listener){
               this.listener=listener;
            }
            public void onClickProcess(){
               if(listener != null){
                  listener.onClick();
               }
            }
         }
         ```
         ```java
         package c.inner;

         public class AnonymousSample {
            public static void main(String args[]){
               AnonymousSample sample = new AnonymousSample();
               sample.setButtonListener();
            }
            public void setButtonListener(){
               MagicButton button = new MagicButton();
               MagicButtonListener listener = new MagicButtonListener();
               button.setListener(listener);
               button.onClickProcess();
            }
            class MagicButtonListener implements EventListener{
               public void onClick(){
                  System.out.println("Magic Button Clicked !!!");
               }
            }
         }
         ```
      - 실제 GUI에서 이 예제처럼 별도로 onClickProcess() 메소드를 실행하지는 않는다. 화면이 클릭 되었을 때 MagicButtonListener에 있는 onClick() 메소드가 수행되게 된다. 여기서는 실제 해당 메소드가 수행되는지를 확인하기 위해서 메소드를 호출한 것이다.
      - 익명 클래스를 만들 수도 있다.

         ```java
         public void setButtonListenerAnonymous(){
            MagicButton button = new MagicButton();
            botton.setListener(new EventListener(){
               public void onClick(){
                  System.out.println("Magic Button Clicked!!!");
               }
            });
            button.onClickProcess();
         }
         ```
      - setListener() 메소드를 보면 new EventListener()로 생성자를 호출한 후 바로 중괄호를 열었다. 그 중괄호 안에는 onClick()메소드를 구현한 후 중괄호를 닫았다. 이것이 바로 "익명클래스"이다.
      - 주의할 점은 괄호와 세미콜론이다. setListener() 메소드를 호출하는 과정 내에 익명 클래스가 있는 것이기 때문에 이와 같이 소괄호를 닫고 세미콜론을 해 줘야한다.
      - 클래스를 만들고 호출하면 그 정보는 메모리에 올라간다. 클래스를 많이 만들수록 메모리가 많이 필요하고, 앱을 시작할 때 더 많은 시간이 소요된다.

## 8. 어노테이션(Annotation)
### 1. 어노테이션이란?
 1. 클래스나 메소드, 변수 등의 선언시에 @를 사용하는 것
 2. Metadata라고도 불린다.
 3. 사용할 때 
   1. 컴파일러에게 정보를 알려줄 때
   2. 컴파일할 때와 설치시의 작업을 지정하거나
   3. 실행할 떄 별도의 처리가 필요할 때
 4. @Override
   1. 해당 메소드가 부모 클래스에 있는 메소드를 Override 했다는 것을 명시적으로 선언한다.
 5. @Deprecated
   1. 클래스나 메소드가 더이상 사용되지 않는 경우에 컴파일러에게 알려주는 것
 6. @SupressWarnings
   1. 경고가 뜰 때 경고해줄 필요 없다고 컴파일러에게 이야기하는 것
   2. 코드
   ```java
   public class AnnotationDeprecated{
      @Deprecated
      public void noMoreUse(){    
      }
   }
   ```
   ```java
   public class AnnotationSample{
      @SuppressWarnings("deprecation")
      public void useDeprecated(){
         AnnotationDeprecated child = new AnnotationDeprecated();
         child.noMoreUse();
      }
   }
   ```
      - 소괄호 속에 문자열을 넘겨주었다. 어노테이션의 종류에 따라서, 속성값을 지정하는 것도 존재한다.

## 9. Java Gabage Collection

### 'stop-the-world'
1. GC를 실행하기 위해 JVM이 앱 실행을 멈추는 것이다.
2. stop-the-world가 발생하면 GC를 실행하는 쓰레드를 제외한 나머지 쓰레드는 모두 작업을 멈춘다.
3. GC 작업을 완료한 이후에야 중단했던 작업을 다시 시작한다. 
4. 어떤 GC 알고리즘을 사용하더라도 stop-the-world는 발생한다.

### Garbage Collector는 두가지 가정 하에 만들어졌다.
1. week generational hypothesis
   1. 대부분의 객체는 금방 접근 불가능 상태가 된다.
   2. 오래된 객체에서 젊은 객체로의 참조는 아주 적게 존재한다.
2. HotSpot VM
   1. 위의 가설의 장점을 최대한 살리기 위해서 HotSpot VM에서는 크게 2가지로 물리적 공간을 나누었다.
      1. Young 영역 : 새롭게 생성한 객체의 대부분이 여기에 위치한다. 대부분의 객체가 금방 접근 불가능 상태가 되기 때문에 매우 많은 객체가 Young 영역에 생성되었다가 사라진다. 이 영역에서 객체가 사라질때 Minor GC가 발생한다고 말한다. 


