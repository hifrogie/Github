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
    - 
