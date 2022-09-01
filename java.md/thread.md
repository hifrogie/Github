## 11. Thread
### 1. Thread
1. java명령어를 사용하여 클래스를 실행시키는 순간 자바 프로세스가 시작되고, main() 메소드가 수행되면서 하나의 쓰레드가 시작되는 것이다.
2. 많은 쓰레드가 필요하다면 main()메소드에서 쓰레드를 생성해주면 된다.
3. 쓰레드를 만든 이유
    - 프로세스를 하나 시작하려면 많은 자원이 필요하다.
    - JVM은 기본적으로 아무런 옵션 없이 실행하면 OS마다 다르지만, 적어도 32MB~64MB의 물리 메모리를 점유한다.
    - 쓰레드는 1MB 이내의 메모리를 점유한다.
    - 쓰레드를 경량 프로세스(light process)라고도 부른다.

### 2. Runnable 인터페이스와 Thread 클래스
1. 쓰레드를 생성하는 방법은 두 가지가 있다. 
2. Runnable 인터페이스를 사용하는 것과 Thread클래스를 사라용하는 방법이 있다.
3. Thread 클래스는 Runnable 인터페이스를 구현한 클래스이다.
4. 모두 java.lang 패키지에 있다. 즉, import할 필요가 없다.
5. 두 가지 방법을 제공하는 이유
    - 어떤 클래스가 어떤 다른 클래스를 extends를 사용해 확장해야 하는 상황인데, 쓰레드로 구현해야할때 인터페이스를 사용한다.

### 3. Runnable 인터페이스

|리턴 타입|메소드 이름 및 매개 변수|설명|
|:-----:|:----------------:|:-:|
|void|run()|쓰레드가 시작되면 수행되는 메소드|

- 쓰레드가 수행되는 우리가 구현하는 메소드는 run()메소드다.
- 쓰레드를 시작하는 메소드는 start()이다.

### 4. Thread 클래스의 생성자

|생성자|설명|
|:--:|:-:|
|Thread()|새로운 쓰레드를 생성한다.|
|Thread(Runnable target)|매개 변수로 받은 target 객체의 run()메소드를 수행하는 쓰레드를 생성한다.|
|Thread(Runnable target,String name)|매개 변수로 받은 target 객체의 run()메소드를 수행하고, name이라는 이름을 갖는 쓰레드를 생성한다.|
|Thread(String name)|name이라는 이름을 갖는 쓰레드를 생성한다.|
|Thread(ThreadGroup group,Runnable target)|매개 변수로 받은 group의 쓰레드 그룹에 속하는 target 객체의 run()메소드를 수행하는 쓰레드를 생성한다.|
|Thread(Group group,Runnable target, String name)|매개 변수로 받은 group의 쓰레드 그룹에 속하는 target 객체의 run()메소드를 수행하고, name이라는 이름을 갖는 쓰레드를 생성한다.|
|Thread(ThreadGroup group,Runnable target,String name,long stackSize)|매개 변수로 받은 group의 쓰레드 그룹에 속하는 target 객체의 run()메소드를 수행하고, name이라는 이름을 갖는 쓰레드를 생성한다. 단 해당 쓰레드의 스택크기는 stackSize 만큼만 가능하다.|
|Thread(ThreadGroup group,String name)|매개 변수로 받은 group의 쓰레드 그룹에 속하는 name이라는 이름을 갖는 쓰레드를 생성한다.|