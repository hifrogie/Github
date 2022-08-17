### 목차
### 1. [예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception)
 1. [예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception-1)
 2. [try-catch](https://github.com/hifrogie/Github/blob/main/java.md#2-try-catch)
 3. [예외의 종류는 3가지](https://github.com/hifrogie/Github/blob/main/java.md#3-%EC%98%88%EC%99%B8%EC%9D%98-%EC%A2%85%EB%A5%98%EB%8A%94-3%EA%B0%80%EC%A7%80)
 4. [java.lang.Throwable](https://github.com/hifrogie/Github/blob/main/java.md#4-javalangthrowable)
 5. [Throwable의 생성자](https://github.com/hifrogie/Github/blob/main/java.md#5-throwable%EC%9D%98-%EC%83%9D%EC%84%B1%EC%9E%90)
 6. [Throwable클래스에 선언되어있고, Exception클래스에서 Overriding한 메소드](https://github.com/hifrogie/Github/blob/main/java.md#6-throwable-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90-%EC%84%A0%EC%96%B8%EB%90%98%EC%96%B4-%EC%9E%88%EA%B3%A0-exception-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-overriding%ED%95%9C-%EB%A9%94%EC%86%8C%EB%93%9C)
 7. [throw와 throws](https://github.com/hifrogie/Github/blob/main/java.md#7-throw%EC%99%80-throws)
 8. [예외 만들기](https://github.com/hifrogie/Github/blob/main/java.md#7-throw%EC%99%80-throws)
 9. [자바 예외 처리 전략](https://github.com/hifrogie/Github/blob/main/java.md#9-%EC%9E%90%EB%B0%94-%EC%98%88%EC%99%B8-%EC%B2%98%EB%A6%AC-%EC%A0%84%EB%9E%B5)
### 2. String
## 1. 예외
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

## 2. String
### 1. String 클래스 선언부
  1. 코드
   ```java
   public final class String extends Object implements Serializable, Comparable<String>, CharSequence
   ```
  2. Serializable
  - 인터페이스를 implements 한 클래스는 선언되어 있는 메소드의 몸통을 구현해야만 한다. 하지만 Serializable 인터페이스는 구현해야 하는 메소드가 하나도 없는 인터페이스다.
  - Serializable 인터페이스를 구현한다고 선언해 놓으면 해당 객체를 파일로 저장하거나 다른 서버에 전송 가능한 상태가 된다.
  3. Comparable<String>
  - 이 인터페이스는 compareTo()라는 메소드 하나만 선언되어 있다.
  - compareTo() 메소드는 매개 변수로 넘어가는 객체와 현재 객체가 같은지를 비교하는 데 사용된다.
  - equals() 메소드와 다른 점은 compareTo() 메소드의 리턴 타입은 int다.
  - compareTo() 메소드는 같으면 0이지만 순서 상으로 앞에 있으면 -1, 뒤에 있으면 1을 리턴한다. 객체의 순서를 처리할 때 유용하다.
  - <String>은 generic이다. generic은 클래스나 메소드에서 사용할 내부 데이터 타입을 컴파일 시에 미리 지정하는 방법
  4. CharSequence
  - 이 인터페이스는 해당 클래스가 문자열을 다루기 위한 클래스라는 것을 명시적으로 나타내는 데 사용된다.
### 2. String 생성자
   1. 용어
      1. Character Set(캐릭터 셋)
      - 문자의 집합을 의미하며, 특정 나라의 글자를 말한다.
      2. Decoding(디코딩)
      - 일반적으로 암호화되어 있거나 컴퓨터가 이해할 수 있는 값들을 알아보기 쉽게 변환하는 것을 말한다.
   2. String 클래스의 생성자
      1. String()
      - 비어있는 String 객체를 생성한다.
      - String name = null;
      - 위의 코드가 더 효율적이다.
      2. String(byte[] bytes)
      - 현재 사용중인 플랫폼의 캐릭터 셋을 사용하여 제공된 byte배열을 디코딩한 String 객체를 생성한다.
      3. String(byte[] bytes, Charset charset)
      - 지정된 캐릭터 셋을 사용하여 제공된 byte 배열을 디코딩한 String 객체를 생성한다.
      4. String(byte[] bytes, String charsetName)
      - 지정한 이름을 같는 캐릭터 셋을 사용하여 지정한 byte 배열을 디코딩한 String 객체를 생성한다.
      5. String(byte[] bytes, int offset, int length)
      - 현재 사용중인 플랫폼의 기본 캐릭터 셋을 사용하여 지정한 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      6. String(byte[] bytes, int offset, int length, Charset charset)
      - 지정된 캐릭터 셋을 사용하여 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      7. String(byte[] bytes, int offset, int length, String charsetName)
      - 지정한 이름을 갖는 캐릭터 셋을 사용하여 byte 배열의 일부를 디코딩한 String 객체를 생성한다.
      8. String(char[] value)
      - char 배열의 내용들을 붙여 String 객체를 생성한다.
      9. String(char[] value, int offset, int count)
      - char 배열의 일부 내용들을 붙여 String 객체를 생성한다.
      10. String(int[] codePoints, int offset, int count)
      - 유니코드 코드 위치(Unicode code point)로 구성되어 있는 배열의 일부를 새로운 String 객체를 생성한다.
      11. String(String original)
      - 매개 변수로 넘어온 String과 동일한 값을 갖는 String 객체를 생성한다. 복제본을 생성한다.
      12. String(StringBuffer buffer)
      - 매개 변수로 넘어온 StringBuffer 클래스에 정의 되어 있는 문자열의 값과 동일한 String 객체를 생성한다.
      13. String(StringBuilder builder)
      - 매개 변수로 넘어온 StringBuilder 클래스에 정의되어 잇는 문자열의 값과 동일한 String 객체를 생성한다.
   3. getBytes()
      1. 생성자의 매개 변수로 받는 byte배열을 생성하는 방법이다.
      2. getBytes()
         1. getBytes()
            1. 리턴 타입 : byte[]
            2. 기본 캐릭터 셋의 바이트 배열을 생성한다.
            3. 같은 프로그램 내에서 문자열을 byte배열로 만들 때 사용
         2. getBytes(Charset charset)
            1. 리턴 타입 : byte[]
            2. 지정한 캐릭터 셋 객체 타입으로 바이트 배열을 생성한다.
            3. 다른 시스템에서 전달 받은 문자열을 byte 배열로 변환 할때 사용. 서로 다른 캐릭터 셋을 사용할 수 있기 때문이다.
         3. getBytes(String charsetName)
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
            3. 코드
            ```java
            public void checkMatch() {
               String text = "This is a text";
               String compare1 = "is";
               String compare2 = "this";
               System.out.println(text.regionMatches(2, compare1, 0, 1));
               System.out.println(text.regionMatches(5, compare1, 0, 2));
               System.out.println(text.regionMatches(true,0 ,compare2, 0, 4));
            }
            ```
            4. 각 char의 위치
            
            |T|h|i|s| |i|s| |a| |t|e|x|t|
            |-|-|-|-|-|-|-|-|-|-|-|-|-|-|
            |0|1|2|3|4|5|6|7|8|9|10|11|12|13|
