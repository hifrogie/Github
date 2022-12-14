## 7. JVM과 DALVIK VM과 ART의 차이
### 1. JVM
1. ByteCode -> interpret(해석) -> 각 플랫폼에 맞는 기계어로 번역 -> 프로그램 실행
2. 장점 : WORA(write once read anywhere),OS에 구애 받지 않고 해당 OS에 맞는 기계어로 번역됨
3. 단점 : Native 언어들에 비해 속도가 느리다.
    - Native : 운영체제를 만들 때 사용한 프로그래밍 언어로 만든 프로그램

### 2. Dalvik VM
1. dex file을 Dalvik machine 위에 올리는 방식
    - dex라는 파일 포맷 : Java로 짜여진 코드가 컴파일 되어 번역된 Bytecode들과 해당 Bytecode들의 구조에 대한 설계를 포함하고 있다.
2. 라이선스 문제로 인해 JVM 대신 Java 코드를 이용할 수 있도록 개발됨
3. Bytecode -> interpret(해석) -> 실행 -> 개선 -> 네이티브 코드로 변환 (JIT, Just in Time 컴파일 방식)
    - JIT 컴파일러 : 런타임시 바이트 코드를 원시 시스템 코드로 컴파일하여 java 애플리케이션의 성능을 향상시키는 런타임 환경의 컴포넌트 입니다.
4. 장점 : 다양한 하드웨어나 아키텍쳐에서 실행 할 수 있는 장점(기존 JVM의 특징)
    - 아키텍쳐 : 컴퓨터 시스템의 하드웨어 구조
5. 단점 : 성능과 배터리에 악영향, JIT compile된 코드가 올라가 메모리가 늘어남

### 3. ART 방식(Android 4.4 Kitkat 이후)
1. machine 위에서 OAT file을 돌리는 방식, VM이 아닌 런타임시 사용되는 라이브러리
    - oat file : 안드로이드 앱의 로드 시간을 단축하기 위해 Android 운영체제에서 생성됩니다. 앱이 설치 되면 Android는 자동으로 앱 데이터를 최적화하고 해당 oat 파일을 생성합니다. 안드로이드는 이 파일을 사용하여 앱을 더 빠르게 로드하여 사용자에게 더 나은 경험을 제공합니다.
2. 앱을 설치할 때 완전히 네이티브 코드로 변환되어 설치 됨(AOT 컴파일, Ahead-Of-Time 컴파일)
    - AOT 컴파일 : 목표 시스템의 기계어와 무관하게 중간 언어 형태로 배포된 후 목표 시스템에서 인터프리터나 JIT컴파일 등 기계어 번역을 통해 실행되는 중간 언어를 미리 목표 시스템에 맞는 기계어로 번역하는 방식을 지칭한다.
3. 장점 : 코드 Interpret 및 JIT compile 시간을 제거하여 performance가 향상됨
4. 단점: 설치시점에 소스코드를 번역하여 설치가 느리고, 파일을 따로 저장하기 때문에 용량이 커짐

### 4. 컴파일 방식 변화 과정(Dalvik VM -> ART)
1. 초창기(Android 4.4,Kitkat)
    - 호환성이 제대로 보장되지 않았다.
    - Dalvik에서 작동하던 앱들이 ART에서 죽는 현상이 발생함.
2. Android 5.0, Lolipop 이후
    - ART가 기본 런타임 됨
3. Android 7.0, Nougat 이후
    - AOT 방식과 JIT 방식을 조합
4. Android 8.0, Oreo 이후
    - ART 방식의 개선이 이뤄져 많은 문제점이 해결

### 5. JIT Compiler vs AOT Compiler
- Dalvik과 ART의 가장 큰 차이는 컴파일 방식이 다르다.
1. JIT Compiler(Dalvik)
    - 앱 실행 시 컴파일
    - 설치 시 컴파일을 하지 않기 때문에 AOT보다 설치 속도가 빠름
    - 실행 시 컴파일을 하기 때문에 AOT에 비해 실행 속도 느림
    - 단점 : 배터리 소모가 많아지고, 한번에 읽는 방식이기 때문에 화면 전환 시 속도도 느리다.
2. AOT Compiler(ART)
    - 앱 설치 시 컴파일
    - 설치 시 컴파일을 완료하기 때문에 JIT에 비해 설치 속도 느림
    - 실행시 컴파일을 하지 않기 때문에 JIT에 비해 실행 속도 빠름
    - 장점 : 사용자의 대기 시간이 거의 없음
    - 단점 : 설치 시 컴파일된 파일을 따로 저장하기 때문에 프로그램 크기가 증가 
