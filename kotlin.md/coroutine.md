## 17. 코루틴
### 1. 코루틴이란?
1. 코루틴은 비동기 코드를 처리하는 동시성 디자인 패턴이다.
2. 코루틴은 메인 쓰레드를 차단하고 앱이 응답하지 않게 할수 있는 장시간 실행 task를 관리하는데 도움이 된다.

### 2. 특징
1. 경량 : 코루틴이 실행될 때 차단되지 않는 suspension의 지원 덕분에 싱글 쓰레드에서 코루틴을 실행할수 있다. 일시 중단은 동시작업을 지원하면서 차단보다 메모리를 절약합니다.
2. 적은 메모리 누수 : scope 안에서 structured concurrency를 사용하여 작업을 실행하라
    - structured concurrency : 코루틴의 수명을 정하는 coroutineScope, 새로운 코루틴은 coroutinescope에서 시작할 수 있다.
    - coroutineScope : 코루틴 빌더(launch, async)는 CoroutineScope의 확장이다. ex) CoroutineScope(), MainScope()
3. built-in cancellation support : 취소는 코루틴 계층을 실행하는 것으로 자동적으로 전파된다.
4. jetpack 통합 : jetpack 라이브러리에는 코루틴 지원을 제공하는 확장이 포함되어 있습니다. 일부 라이브러리는 structured concurrency에 사용가능한  자체 코루틴 범위를 제공한다.

### 3. 코드 분석

```kotlin
fun main() = runBlocking { // this: CoroutineScope
    launch { // launch a new coroutine and continue
        delay(1000L) // non-blocking delay for 1 second (default time unit is ms)
        println("World!") // print after delay
    }
    println("Hello") // main coroutine continues while a previous one is delayed
}
```

1. launch 
    - 코루틴 빌더이다.
    - 이것은 남은 코드와 함께 새로운 코루틴을 동시에 시작한다.
    - 쓰레드를 차단하지 않고 새로운 코루틴을 시작한다.
    - Job을 반환한다.
    - job이 삭제되면 코루틴도 삭제된다.
    - job : 코루틴을 컨트롤 하기 위해 사용 됨
2. runBlocking
    - 코루틴 빌더이다.
    - 새 코루틴을 실행하고 완료될 떄 까지 현재 스레드를 차단합니다. 
    - 이 함수는 코루틴에서 사용하면 안됩니다.
    - main 함수 및 테스트에서 사용하기 위해 일시 중단 스타일로 작성된 라이브러리에 일반 차단 코드를 연결하도록 설계되었습니다.
3. delay
    - 코루틴을 특정 시간 동안 지연 시킬 수 있다.
    - 다른 실행하는 코루틴과 스레드를 차단하지 않는다. 

### 4. structured concurrency
1. 부모의 operation이 끝나기 전에 자식의 operation이 끝남을 보장하는 것을 structed concurrency라고 한다.
2. 부모-자식간의 관계에 대한 상호작용
    1. 자식 코루틴은 부모 코루틴으로 부터 컨텍스트를 상속 받는다.( 해당 컨텍스트를 덮어쓰는 것도 가능)
    2. 부모 코루틴은 자식 코루틴이 모두 완료될 때 까지 일시중단된다.
    3. 부모 코루틴이 cancel 되었을 때, 자식 코루틴들도 모두 cancel 된다.
    4. 자식 코루틴에서 예외가 발생하여 부모 코루틴으로 전파되었을 때, 부모 코루틴 또한 종료된다.
3. 해당 scope에 있는 모든 코드의 수행을 보장하기에 데이터 유실이나 누수가 일어나지 않습니다.

### 5. Coroutine Builder
1. Scope
    1. Scope : 코루틴이 실행되는 범위
    2. GlobalScope : Application이 종료될 때 까지 존재하는 코루틴, Activity가 종료되어도 존재하는 코루틴이므로 구분해서 사용해야함
2. Coroutine Builder
    1. CoroutineScope의 확장함수로 다양한 요구사항에 맞게 개별적인 Coroutine을 만드는 방법
    2. 종류
        1. launch() : Job 반환
            - 결과가 없는 코루틴을 생성하는 빌더, 여기서 결과는 반환 인스턴스가 아닌 결과 값을 의미
            - 반환하는 job인스터스는 생성된 해당 코루틴을 제어하는데 사용
        2. asnyc() : Deferred< T> 반환
            - 결과를 가지는 코루틴을 생성하는 빌더
            - 반환하는 Deferred< T>로 코루틴을 제어하고 결과를 받을 수있다.
            - 결과를 받는 다는 의미는 Deffered의 await() 함수를 통해 코루틴 영역의 마지막라인(결과)를 받을 수 있다.
            - Deffered< T>는 지연객체라고 생각하면 좋다. 내가 원하는 시점에 await()로 결과를 받는다.
        3. withContext() : T 반환
            - 결과 값을 반환
            - Deferred< T>로 객체를 반환하지 않고, 결과(T)를 그자리에서 반납
        4. runBlocking : T 반환
            - runBlocking은 Scope 내의 코루틴들이 모두 완료할 때까지 스레드를 점유한다.
            - Main()에서 CoroutineScope로 코루틴을 생성하고 실행할 경우 점유하지 않기 때문에 Main()은 코루틴이 실행 중임에도 본인의 함수는 끝나고 종료된다.
        5. actor() : SendChanner< E> 반환
            - 채널을 통해 코루틴 블럭(Scope)와 외부에서 통신ㅇ르 통해 전송과 처리의 루틴을 실행하는 빌더이다.
            - actor 빌더는 SendChanner< E>를 반환, Send채널을 통해 actor()블록으로 채널을 통해 전송 할 수 있다.
            - actor{}블록 내부는 수신자(Receiver)가 되고 반환된 SendChanner이 송신자(Sender)라고보면 된다.
        6. produce() : ReceiveChanner< E> 반환
            - 채널을 통해 전송과 처리 루틴을 실행하는 빌더이다.
            - produce{} 블록 내부는 송신자(Sender)가 되고 반환된 ReceiveChanner이 수신자(Receiver)가 된다.