## 1. [예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception)
 ### 목차
     1.[예외 Exception](https://github.com/hifrogie/Github/blob/main/java.md#1-%EC%98%88%EC%99%B8-exception-1)
     2.[try-catch](https://github.com/hifrogie/Github/blob/main/java.md#2-try-catch)
     3.[예외의 종류는 3가지](https://github.com/hifrogie/Github/blob/main/java.md#3-%EC%98%88%EC%99%B8%EC%9D%98-%EC%A2%85%EB%A5%98%EB%8A%94-3%EA%B0%80%EC%A7%80)
     4.[java.lang.Throwable](https://github.com/hifrogie/Github/blob/main/java.md#4-javalangthrowable)
     5.[Throwable의 생성자](https://github.com/hifrogie/Github/blob/main/java.md#5-throwable%EC%9D%98-%EC%83%9D%EC%84%B1%EC%9E%90)
     6.[Throwable클래스에 선언되어있고, Exception클래스에서 Overriding한 메소드](https://github.com/hifrogie/Github/blob/main/java.md#6-throwable-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90-%EC%84%A0%EC%96%B8%EB%90%98%EC%96%B4-%EC%9E%88%EA%B3%A0-exception-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-overriding%ED%95%9C-%EB%A9%94%EC%86%8C%EB%93%9C)
### 1. 예외 Exception
   - 예상한, 예상치 못한 일이 발생하는 것을 미리 예견하고 안전장치 하는 것
### 2. try-catch

     ```
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
        1. 가장 첫 줄에는 예외 메세지 출력, 두 번째줄 부터는 예외가 발생하게된 메소드들의 stack trace를 출력해줌. 
            
       