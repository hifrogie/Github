## 12. I/O
### 1. I/O
1. I/O는 어떨 때 사용하나요?
    - 파일에 읽거나 저장할 일이 있을 때
    - 다른 서버나 디바이스로 보낼 일이 있을 떄 
2. Stream
    - 스트림 : 끊기지 않고 연속적인 데이터
    - I/O를 처리하기 위해서 java.io 패키지에서 Stream 클래스를 제공한다.
    - 읽는 작업은 IpoutStream을 통해서, 쓰는 작업은 OutputStream을 통해서 작업하도록 되어있다.
3. Reader와 Writer
    - char 기반의 문자열로만 되어 있는 파일은 Reader와 Writer클래스로 처리한다.
4. NIO
    - Buffer와 Channel 기반으로 데이터를 처리한다.

### 2. File과 Files 클래스
1. File
    - java.io 패키지에 있다.
    - 파일과 파일 경로(path)정보도 포함
    - File 클래스는 정체가 불분명하고 symbolic link와 같은 유닉스 계열의 파일에서 사용하는 몇몇 기능을 제대로 제공하지 못한다.
2. Files
    - Java7 부터는 NIO2가 등장하면서 Files라는 클래스에서 File 클래스에 있는 메소드들을 대체하여 제공한다.

### 3. InputStream과 OutputStream은 자바스트림의 부모들이다.
1. InputStream
    - 데이터를 읽을 때 InputStream의 자식 클래스를 통해서 읽으면 된다.
    - 선언문 : public abstract class InputStream extends Closable
    - abstract 클래스로 선언되어 있음
    - Closable 인터페이스 
        - close()란 메소드만 있음
        - close() : 스트림에서 작업중인 대상을 해제한다. 이 메소드를 수행한 이후에는 다른 메소드를 사용하여 데이터를 처리할 수 없다.
        - java.io 패키지에 있는 클래스를 사용할 때에는 하던 작업이 종료되면 close() 메소드로 항상 닫아주어야한다.
        - 리소스 : 파일이 될 수도 있고 네트워크 연결도 될 수있다. 스트림을 통해서 작업할 수 있는 모든 것
2. OutputStream
    - 데이터를 쓸 때 OutputStream의 자식 클래스를 통해서 쓰면 된다.
    - 선언문 : public abstract class OutputStream extens Object implements Closable, Flushable
    - Flushable 인터페이스 
        - flush() 메소드만 선언되어 있다.
        - flush() : 버퍼에 쓰려고 대기하고 있는 데이터를 강제로 쓰도록 한다.
        - buffer : IputStream과 InputStreamReader를 보완하고 합쳐서 탄생한 입출력의 최종 형태
    
### 4. Reader와 Writer
1. Reader와 Writer는 char 기반의 문자열을 처리 하기 위한 클래스
2. Reader
    - 선언부 : public abstract class Reader extends Object implements Readable, Closeable
3. Writer
    - 선언부 : public abstract class Writer extends Object implements Appendable, Closeable, Flushable
    - Appendable 인터페이스 : 각종 문자열을 추가하기 위해 선언됨

### 5. blocking I/O와 non blocking I/O
1. blocking I/O
    - I/O 작업이 진행되는 동안 유저 프로세스가 자신의 작업을 중단한 채, I/O가 끝날 때까지 대기하는 방식을 의미한다.
    - 어플리케이션에서 Read()를 호출해 커널에 read I/O를 요청하면, read가 끝날 때까지 application은 block이 되어 다른 작업을 하지 못한다.
    - 이는 read I/O가 수행될 때 까지는 어플리케이션이 다른 작업을 수행하지 못한다는 것을 의미한다.
    - 커널 : 컴퓨터 운영 체제의 핵심이 되는 컴퓨터 프로그램으로 시스템의 모든 것을 완전히 통제한다.
2. non blocking I/O
    - A함수가 I/O 작업을 호출했을 때 I/O작업이 완료될때 까지 A함수의 작업을 중단하지 않고 I/O 호출에 즉시 리턴하고, A함수가 이어서 다른 일을 수행할 수있도록 하는 방식을 의미한다.
    - read I/O를 하기 위해 system call 을 수행하면, 커널의 I/O 작업 완료 여부와는 무관하게 즉시 응답한다. 이는 커널이 시스템 콜을 받자마자 CPU 제어권을 다시 어플리케이션에게 넘겨주고, 따라서 어플리케이션은 I/O 작업이 완료되기 전에 다른 작업을 수행할 수있다. 
    - 그리고 어플리케이션은 다른 작업들을 수행하다가 중간중간 시스템 콜을 보내서 I/O가 완료됐는지 커널에게 물어보고, 완료되면 I/O작업을 완료한다.
    - system call : 운영체제의 커널이 제공하는 서비스에 대해 응용 프로그램의 요청에 따라 커널에 접근하기 위한 인터페이스이다.