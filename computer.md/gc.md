## 11. Java Reference와 GC
### 1. GC
1. Java의 가비지 컬렉터는 그 동작 방식에 따라 매우 다양한 종류가 있지만 공통적으로 크게 다음 2가지 작업을 수행한다고 볼 수 있습니다.
    1. heap 내의 객체 중에서 garbage를 찾아낸다.
    2. 찾아낸 garbage를 처리해서 힙의 메모리를 회수한다.
2. 최초의 Java에서는 이들 가비지 컬렉션(garbage collection 이하 GC) 작업에 애플리케이션의 사용자 코드가 관여하지 않도록 구현되어 있었습니다.
3. 그러나 위 2가지 작업에서 좀 더 다양한 방법으로 객체를 처리하려는 요구가 있었습니다.
4. 이에 따라 JDK 1.2부터는 java.lang.ref 패키지를 추가해 제한적이나마 사용자 코드와 GC가 상호작용할 수 있게 하고 있습니다.
5. java.lang.ref 패키지는 전형적인 객체 참조인 strong reference 외에도 soft, weak, phantom 3가지의 새로운 참조 방식을 각각의 Reference 클래스로 제공합니다.
6. 이 3가지 Reference 클래스를 애플리케이션에 사용하면 앞서 설명하였듯이 GC에 일정 부분 관여할 수 있고, LRU(Least Recently Used) 캐시 같이 특별한 작업을 하는 애플리케이션을 더 쉽게 작성할 수 있습니다.
7. 이를 위해서는 GCㅇ에 대해서도 잘 이해해야할 뿐 아니라, 이들 참조 방식의 동작도 잘 이해할 필요가 있습니다.

### 2. GC와 Reachability
1. Java GC는 객체가 가비지인지 판별하기 위해서 reachabliliy라는 개념을 사용한다.
2. 어떤 객체에 유효한 참조가 있으면 reachable로 없으면 unreachable로 구별하고, unreachable 객체를 가비지로 간주해 GC를 수행한다.
3. 한 객체는 여러 다른 객체를 참조하고, 참조된 다른 객체들도 마찬가지로 또 다른 객체들을 참조할 수 있으므로 객체들을 참조 사슬을 이룬다.
4. 이러한 상황에서 유효한 참조 여부를 파악하려면 항상 유효한 최초의 참조가 있어야 하는데 이를 객체 참조의 root set이라고 한다.
5. JVM에서 메모리 영역인 런타임 데이터 영역을(runtime data area)의 구조를 그림으로 그리면 다음과 같다.
![런타임 이미지](https://d2.naver.com/content/images/2015/06/helloworld-329631-1.png) 
6. 런타임 데이터 영역은 위와 같이 스레드가 차지하는 영역들과, 객체를 생성 및 보관하는 하나의 큰 힙, 클래스 정보가 차지하는 영역인 메서드 영역으로 크게 세 부분으로 나눌 수 있다. 
7. 위 그림에서 객체에 대한 참조는 화살표로 표시되어있다.
8. 힙에 있는 객체들에 대한 참조는 다음 4가지 종류 중 하나이다.
    1. 힙 내의 다른 객체에 의한 참조
    2. Java 스택, 즉 Java 메서드 실행 시에 사용하는 지역 변수와 파라미터들에 의한 참조
    3. 네이티브 스택, 즉 JNI(Java Native Interface)에 의해 생성된 객체에 대한 참조
    4. 메서드 영역의 정적 변수에 의한 참조
9. 이들 중 힙내의 다른 객체에 의한 참조를 제외한 나머지 3개가 root set으로, reachability를 판가름하는 기준이 된다.
10. reachability를 더 자세히 설명하기 위해 root set과 힙 내의 객체를 중심으로 다시 그리면 다음과 같다.

