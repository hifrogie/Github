## 6. Jetpack 라이브러리
### 1. jetpack 라이브러리
1. jetpack : 앱 개발시 필요한 라이브러리의 모음
2. 특징 
    1. androidx로 시작하는 패키지 명
    2. 앱 개발시 필요한 권장 아키택쳐 제공
    3. 플랫폼 API에서 제공하지 않는 다양한 기능 제공
            - 플랫폼 API : ART(Android runtime)에서 제공하는 안드로이드 앱의 핵심 라이브러리(String, Date, Activity, TextView등)
    4. API 레벨 호환성 문제 해결 : 목적이 같은 클래스를 제트팩에서 제공한다면 제트팩 클래스를 쓰는 것이 좋음
### 2. jetpack 라이브러리의 내용
1. activity, appcompat, recyclerview 많은 내용이 있었다.
2. AppCompat
    1. appcompat의 api를 제공한다.
    2. build.gradle에 추가할 의존성도 제공한다.
    3. 버전마다 달라진 내용도 알려준다. 
### 3. Jetpack이 나오게 된 배경
1. Jetpack이 나오기 전 Support library라고 하는 라이브러리 모음집이 이미 존재 했었는데 여러 문제가 있었다.
2. 이를 개선하면서 새로운 이름을 붙여 다시 나온 것이 jetpack이다.
3. 문제 
    1. support library는 패키지명과 규칙이 모호했다.
    2. 단일 라이브러리로 제공된다.
        1. 서포트 라이브러리는 3만 여개의 함수를 제공하는 단일 라이브러리였다.
        2. 한가지 기능만 추가 할 수 없다.
    3. 바이너리 호환성 제약
        1. 한꺼번에 업데이트하고 다운드레이드 해야 함.
        2. 이를 해결하고자 AndroidX는 위젯 단위의 세분화된 형태로 모듈화해서 라이브러리를 제공하게 되었다.