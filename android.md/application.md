# Application

### 1. Doc 정의
1. 글로벌 애플리케이션 상태를 유지하기 위한 기본 클래스
2. 서브클래스를 만들거나 메니페스트에서 명시적으로 지정해 줌으로써 구현을 제공해 줄 수 있다.
3. application과 application의 하위 클래스는 다른 클래스 보다 먼저 인스턴스화 된다.
4. 일반적으로 application을 서브클래싱 할 필요가 없습니다.
5. 대부분의 상황에서 static singleton은 보다 모듈화된 방식으로 동일한 기능을 제공할 수 있습니다.
6. 싱글톤이 글로벌 context가 필요한 경우 (예: 브로드 캐스트 receiver 등록) 싱글톤의 getInstance()메서드를 호출할 때 context 인수로 Context.getApplicationContext()를 포함합니다.
7. 어떤 값을 액티비티, 서비스등 안드로이드 컴포넌트 사이에서 공유해 사용할 수 있게 해준다.

### 2. 정의
1. 어플리케이션 컴포넌트 사이에서 공동으로 멤버들을 사용할 수 있게 해주는 공유 클래스를 제공 
  - 컴포넌트(안드로이드 4대 구성요소) 
    - 액티비티
    - 서비스
    - 콘텐트 제공자 (content provider)
    - 방송 수신자 (broadcaster receiver)
3. 어디서든 context를 이용한 접근이 가능
    - context는 application이 동작하는 동안의 모든 환경을 핸들링한다.
    - application context : applicationContext
    - activity context : baseContext, this
5. 객체들이 공동으로 접근가능하게 만들려면 첫번째 application class를 상속 받는다. 그리고 필수 함수를 구현하고 사용자가 원하는 기능을 추가한다.
6. 두번째 메니페스트에 상속받아 만든 class를 추가한다.
7. 앱이 시작하면 application을 상속받은 클래스 먼저 생성된다.
