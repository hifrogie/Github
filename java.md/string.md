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