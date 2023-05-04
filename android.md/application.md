# Application

### 1. 정의
1. 글로벌 애플리케이션 상태를 유지하기 위한 기본 클래스
2. 서브클래스를 만들거나 메니페스트에서 명시적으로 지정해 줌으로써 구현을 제공해 줄 수 있다.
3. application과 application의 하위 클래스는 다른 클래스 보다 먼저 인스턴스화 된다.
4. 일반적으로 application을 서브클래싱 할 필요가 없습니다.
5. 대부분의 상황에서 static singleton은 보다 모듈화된 방식으로 동일한 기능을 제공할 수 있습니다.
6. 싱글톤이 글로벌 context가 필요한 경우 (예: 브로드 캐스트 receiver 등록) 싱글톤의 getInstance()메서드를 호출할 때 context 인수로 Context.getApplicationContext()를 포함합니다.
7. 어떤 값을 액티비티, 서비스등 안드로이드 컴포넌트 사이에서 공유해 사용할 수 있게 해준다.
