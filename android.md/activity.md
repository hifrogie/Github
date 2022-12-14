## 9. Activity
## 1. Activity lifecycle
1. onCreate()
    1. 시스템에서 액티비티를 생성할 때 실행되는 이 콜백을 필수적으로 구현해야 합니다.
    2. 액티비티의 필수 구성 요소를 초기화해야 합니다.
    3. 예를 들어 뷰를 만들고 데이터를 바인딩하고 setContentView()를 호출해야한다. 
    4. 이 메서드는 savedInstanceState 매개변수를 수신하는데, 이는 액티비티의 이전 저장 상태가 포함된 Bundle 객체입니다. 이번에 처음 생성된 액티비티의 경우 Bundle 객체의 값은 null 입니다.
2. onStart()
    1. onCreate() 종료되면 액티비티가 시작됨 상태가 되고 액티비티가 사용자에게 표시됩니다.
    2. 이 콜백에는 전면에 나서 대화형이 되기 위한 활동의 최종 준비에 해당하는 내용이 포함 되어있습니다.
    3. onStart()메서드는 매우 빠르게 완료되고 생성된 액티비티와 마찬가지로 액티비티는 시작된 상태에 머무르지 않습니다. 콜백이 완료되면 onResume()메서드를 호출합니다.
3. onResume()
    1. activity가 사용자와 상호 작용하기 직전에 이 콜백을 호출합니다.
    2. 이 시점에서 활동은 활동 스택의 맨 위에 있으며 모든 사용자 입력을 캡쳐합니다.
    3. 앱의 대부분의 핵심 기능은 onResume()메서드에서 구현됩니다.
    4. 방해되는 이벤트가 발생하면 액티비티는 일시중지 상태로 들어가고 onPause() 콜백을 호출함
    5. 액티비티가 일시중지됨 상태에서 재개됨 상태로 오면 시스템임 onResume() 메서드를 다시한번 호출한다. 따라서 onResume()을 구현하여 onPause()중에 해제하는 구성요소를 초기화하고 활동이 재개됨 상태로 전환될 때 필요한 다른 초기화 작업도 수행해야 합니다.
4. onPause()
    1. 액티비티가 포커스를 잃고 paused 상태가 되면 시스템이 호출합니다. 
    2. 액티비티가 포그라운드에 있지 않게 되었다는 것을 나타냄(사용자가 멀티 윈도우 모드에 있을 경우에는 여전히 표시 될 수도 있음)
    2. 사용자가 UI업데이트를 기대하는 경우 Paused상태의 활동은 UI를 계속 업데이트 할 수 있습니다. 예로는 내비게이션 지도 화면을 보여주는 액티비티 입니다. 이러한 액티비티가 초점을 잃더라도 사용자는 UI가 계속 업데이트 되기를 기대합니다.
    3. 응용 프로그램이나 사용자 데이터를 저장하거나 네트워크 호출을 하거나 데이터베이스 트랜택션을 실행하는데 사용해서는 안된다.
    4. 액티비티가 일시중지됨 상태로 전환하면 이 액티비티의 수명 주기와 연결된 모든 수명 주기 인식 구성요소는 ON_PAUSE 이벤트를 수신합니다. 여기에서 수명 주기 구성요소는 구성요소가 포그라운드에 있지 않을 때 실행할 필요가 없는 기능을 모두 정지 할 수 있습니다.
    5. 사용자가 필요로 하지 않을 때 배터리 수명에 영향을 미칠 수 있는 모든 리소스를 해제할 수도 있습니다. 하지만 일시중지된 활동이 멀티 윈도우 모드에서 여전히 보이는 상태일 수 있으므로 UI관련 리소스와 작업을 완전히 해제하거나 조정할 때는 onStop()을 사용하는 것이 좋다.
5. onStop()
    1. 액티비티가 사용자에게 더 이상 표시되지 않으면 시스템이 호출합니다.
    2. 액티비티가 중단됨 상태로 전환하면 이 액티비티의 수명 주기와 연결된 모든 수명 주기 인식 구성요소는 ON_STOP 이벤트를 수신합니다. 여기에서 수명 주기 구성요소는 구성요소가 화면에 보이지 않을 때 실행할 필요가 없는 기능을 모두 정지할 수 있습니다.
    3. onStop()을 사용하여 CPU를 비교적 많이 소모하는 종료 작업을 실행해야한다. 예를 들어 정보를 데이터 베이스에 저장할 시기를 onStop()상태일 때 저장할 수있다.
    4. 액티비티가 중단됨 상태에 들어가면 액티비티 객체는 메모리 안에 머무르게 됩니다. 이 객체가 모든 상태 및 멤버 정보를 관리하지만 창 관리자와 연결되어 있지는 않습니다. 액티비티가 다시 시작되면 이 정보를 다시 호출 합니다.
    5. 액티비티가 다시 시작되면 onRestart()
    6. 액티비티가 실행을 종료하면 시스템은 onDestroy()를 호출
6. onRestart()
    1. 중지된 상태의 액티비티가 다시 시작되려고 할 때 시스템이 이 콜백을 호출합니다.
    2. onRestart() 활동이 중지된 시점부터 활동 상태를 복원합니다.
    3. 이 콜백 뒤에는 항상 onStart()가 옵ㄴ디ㅏ.
7. onDestroy()
    1. 시스템은 액티비티가 소멸 되기 전에 이 콜백을 호출합니다.
    2. onDestroy()는 액티비티 또는 이를 포함한 프로세스가 소멸될 때 활동의 모든 자원이 해제되도록 구현됩니다.
    3. 액티비티가 소멸됨 상태로 전환하면 이 액티비티의 수명주기와 연결된 모든 수명 주기 인신 구성요소는 ON_DESTROY 이벤트를 수신한다.
    4. 여기서 수명 주기 구성요소는 활동이 소멸되기 전에 필요한 것을 정리할 수 있습니다.
    5. 액티비티에 소멸되는 이유를 결정하는 로직을 입력하는 대신 ViewModel 객체를 사용하여 액티비티의 관련 뷰 데이터를 포함해야된다. 액티비티가 구성 변경으로 인해 다시 생성될 경우 ViewModel은 그대로 보존 되어 다음 액티비티 인스턴스에 전달되므로 추가 작업이 필요하지 않습니다. 액티비티가 다시 생성되지 않을 경우 ViewModel은 onCleared()메서드를 호출하여 활동이 소멸되기 전에 모든 데이터를 정리해야 합니다. 이와 같은 두 가지 시나리오는 isFinishing()메서드로 구분할 수 있습니다.
    6. 액티비티가 종료되는 경우 onDestroy()는 액티비티가 수신하는 마지막 수명주기 콜백이 되고 구성변경으로 인해 onDestroy()가 호출되는 경우 시스템이 즉시 새 액티비티 인스턴스를 생성한 다음, 새로운 구성에서 그 새로운 인스턴스에 관해 onCreate()를 호출합니다.
    7. onDestroy() 콜백은 이전의 콜백에서 아직 해제되지 않은 모든 리소스(예:onStop())을 해제해야 합니다.

### 2. Activity 상태 및 메모리에서 제거
1. 시스템은 RAM에 여유 공간이 필요할 때 프로세스를 종료합니다.
2. 시스템이 특정 프로세스를 종료할 가능성은 그 시점의 프로세스 상태에 따라 달라집니다. 그리고 프로세스 상태는 프로세스에서 실행되는 액티비티 상태에 따라 달라집니다.

|종료될 가능성|프로세스 상태|액티비티 상태|
|:-:|:-:|:-:|
|최소|포그라운드(포커스가 있거나 포커스를 가져올 예정)|생성됨,시작됨,재개됨|
|중간|백그라운드 (포커스 상실)|일시중지됨|
|최대|백그라운드(보이지 않음)|중지됨|
|최대|비우기|소멸됨|

3. 시스템은 메모리 공간을 확보하기 위해 절대 액티비티를 직접 종료하지 않습니다. 그 대신 액티비티를 실행하는 프로세스를 종료하여 액티비티와 프로세스에서 실행되는 모든 작업을 함께 소멸 시킵니다.

### 3. 임시 UI 상태 저장 및 복원
1. 시스템 제약으로 액티비티가 소멸되면 viewModel, onSaveInstanceState() 및 로컬 저장소를 결합하여 사용자의 임시 UI 상태를 보존해야 합니다.
2. 인스턴스 상태란?
    1. 시스템이 이전 상태를 복원하기 위해 사용하는 저장된 데이터를 이르는 말
    2. Bundle 객체에 저장된 키-값 쌍의 컬렉션입니다.
    3. 시스템이 시스템 제약(구성 변경 또는 메모리 부족)으로 인해 액티비티를 소멸 시킬 경우, 실제 액티비티 인스턴스는 사라지더라도 시스템에 존재했다는 정보는 남아 있다. 사용자가 액티비티로 다시 돌아가려고 시도하면 시스템은 소멸 당시 액티비티의 상태를 설명하는 저장된 데이터 세트를 사용하여 해당 액티비티의 인스턴스를 생성한다.
    4. Bundle 객체는 메인 스레드에서 직렬화되어야하고 시스템 프로세스 메모리를 사용하므로 소량의 데이터를 보존하는데만 적합합니다. 
    5. 극소량 이상의 데이터를 보존하려면 영구 로컬 저장소, onSavedInstanceState()메서드,ViewModel 클래스로 데이터를 보존하는 복합적인 방ㅇ법을 사용해야 합니다.
3. onSaveInstanceState()를 사용하여 간단하고 가벼운 UI 상태 저장
    1. 액티비티가 정지되기 시작하면 인스턴스 상태 번들에 상태 정보를 저장할 수 있도록 시스템이 onSaveInstanceState() 메서드를 호출합니다.
    2. 이 메서드의 기본 구현은 EditText 위젯 내 텍스트 또는 ListView 위젝의 스크롤 위치와 같은 액티비티의 뷰 계층 구조에 대한 임시 정보를 저장합니다.
    3. 액티비티의 추가적인 인스턴스 상태 정보를 저장하려면 onSaveInstanceState()를 재정의하고, 활동이 예상치 못하게 소멸될 경우 저장되는 Bundle 객체에 키-값 쌍을 추가해야합니다.
    4. onSavedInstanceState()를 재정의할 경우 기본 구현에서 뷰 계층 구조의 상태를 저장하고자 한다면 상위 클래스 구현을 호출해야 합니다.
    5. 영구 데이터(사용자 기본 설정 또는 데이터 베이스 데이터)를 저장하려면 활동이 포그라운드에 있을 때 적절한 기회를 잡아야 합니다. 그럴 기회가 없으면 onStop() 메서드가 호출되었을 때 해당 데이터를 저장해야 합니다.

### 4. 액티비티 간 이동
1. Intent 객체
    1. 시작하고자 하는 액티비티를 정확히 나타내거나, 실행하고자 하는 작업의 유형을 설명합니다.
    2. 시작된 액티비티에서 사용할 소량의 데이터를 포함할 수 있습니다.
2. startActivity()
    1. 새로 시작된 액티비티가 결과를 반환할 필요가 없을 때 현재 액티비티가 startActivity() 메서드를 호출하면 이를 시작할 수 있다.
    2. 실행하고자하는 동작을 설명하는 인텐트를 생성하면 시스템이 적절한 활동을 다른 앱에서 시작합니다.
3. startActivityForResult()
    1. 활동이 종료될 때 결과를 반환 받고자 할 때 사용
    2. 결과는 onActivityResult(int,int,Intent)메서드를 통해 반환됨
    3. 하위 액티비티가 존재하면 setResult(int)를 호출하여 상위 액티비티로 데이터를 반환 할 수 있다. 하위 액티비티는 항상 결과 코드를 제공한다.
    4. 이는 표준 결과인 RESULT_CANCELED,RESULT_OK가 되거나 RESULT_FIRST_USER로 시작하는 임의의 맞춤 값이 될 수 도 있습니다.
    5. 상위 활동은 원래 제공했던 정수 식별자와 함께 onActivityResult(int, int, Intent) 메서드를 사용하여 정보를 수신합니다.
4. 액티비티 A가 액티비티 B를 시작할 떄 발생하는 작업 순서
    1. 액티비티 A의 onPause() 메서드가 실행됩니다.
    2. 액티비티 B의 onCreate(), onStart(), onResume()메서드가 순차적으로 실행됩니다.(이제 사용자 포커스는 액티비티 B에 있습니다.)
    3. 액티비티 A가 더 이상 화면에 표시되지 않는 경우 이 액티비티의 onStop()메서드가 실행됩니다.

### 5. 구성 변경 발생
1. 구성 변경 발생 할 수 있는 이벤트
    1. 가로모드와 세로 모드 간 방향 변경
    2. 언어 또는 입력 기기 변경
2. 구성 변경이 발생하면 생기는 일
    1. 원래 액티비티 인스턴스에는 onPause(), onStop(), onDestroy() 콜백이 트리거 된다.
    2. 새 액티비티 인스턴스에서는 onPause(), onStart(), onResume() 콜백이 트리거 된다.
3. 액티비티 또는 대화상자가 포그라운드로 나옴
    1. 새 액티비티 또는 대화상자가 포그라운드로 나옴에 따라 포커스를 얻고 진행 중인 활동을 부분적으로 가리면 가려진 액티비티는 포커스를 잃고 일시중지됨 상태로 전환됩니다. 그러면 시스템은 그 액티비티에 onPause()를 호출
    2. 가려진 액티비티가 포그라운드로 돌아와서 포커스를 다시 얻으면 시스템은 onResume()을 호출합니다.
    3. 새 액티비티 또는 대화 상자가 포그라운드에 나옴에 따라 포커스를 얻고 진행 중인 액티비티를 완전히 가리면 가려진 액티비티는 포커스를 읽고 중지됨 상태로 전환된다. 시스템음 onPaused()와 onStop()을 빠르게 연속적으로 호출합니다.
    4. 가려진 액티비티의 동일한 인스턴스가 포그라운드로 다시 돌아오면 시스템은 액티비티에 onRestart(), onStart(), onResume()을 호출한다. 인스턴스가 백그라운드로 전환된 가려진 액티비티의 새 인스턴스이면 시스템은 onRestart()를 호출하지 않고 onStart(), onResume()만 호출함
4. 사용자가 뒤로 버튼을 탭함
    1. 액티비티가 포그라운드에 있는데 사용자가 뒤로 버튼을 탭하면 액티비티는 onPaused(), onStop(), onDestroy() 콜백을 거치며 전환된다. 또한 액티비티는 제거될 뿐만 아니라 백 스택에서도 삭제된다.
    2. 이런 상황에서는 onSaveInstanceState() 콜백이 실행되지 않는다는 점을 유의해야합니다.

### 6. Task
1. task(작업)란?
    1. 사용자가 특정 작업을 할 때 상호작용하는 액티비티의 컬렉션
    2. 액티비티는 스택(백 스택)에 각 활동이 열린 순서대로 정렬된다.
2. 백스택의 후입선출 구조
    1. 현재 액티비티가 또 다른 액티비티를 시작하면 새 액티비티가 스택의 맨 위에 푸시되고 포커스를 갖게 됩니다. 이전 액티비티는 스택에 남아있지만 중지됩니다. 액티비티가 중지되면 시스템은 액티비티의 사용자 인터페이스가 갖고 있는 현재 상태를 보존합니다. 
    2. 사용자가 뒤로 버튼을 누르면 현재 액티비티가 스택의 맨 위에서 팝되고(활동이 제거되고) 이전 액티비티를 다시 시작됩니다(UI의 이전 상태가 복원됨). 스택의 액티비티는 다시 정렬되지 않으며 스택에 푸시되고 스택에서 팝될 뿐입니다. 
    3. 현재 액티비티에 의해 시작될 때 스택으로 푸시되고 사용자가 뒤로 버튼을 사용하여 액티비티를 떠날 때 스택에서 팝됩니다.
3. 작업 관리
    1. 앱의 액티비티가 시작될 때 현재 작업 내에 배치되지 않고 새 작업이 시작되게 할 수 있습니다. 또는 액티비티가 시작될 때 백 스택의 맨위에 새 인스턴스가 생성되는 대신 액티비티의 기존 인스턴스가 앞으로 나오도록 할 수 있습니다. 또는 사용자가 작업을 떠날 때 루트 활동을 제외한 모든 활동이 백스택에서 제거 되도록 할 수 있습니다.
    2. < activity > menifest 요소의 속성 및 startActivity()에 전달하는 인텐트 플래그를 사용하여 이러한 모든 작업과 그 외 여러 작업을 할 수 있습니다.
        1. 이 와 관련하여 사용할 수 있는 주요 < activity> 속성
            1. taskAffinity
            2. launchMode
            3. allowTaskReparenting
            4. clearTaskOnLaunch
            5. alwaysRetainTaskState
            4. finishOnTaskLaunch
        2. 사용할 수 있는 주요 인텐트 플래그
            1. FLAG_ACTIVITY_NEW_TASK
            2. FLAG_ACTIVITY_CLEAR_TOP
            3. FLAG_ACTIVITY_SINGLE_TOP
4. 실행 모드 정의
    1. 실행 모드를 통해 액티비티의 새 인스턴스가 현재 작업과 연결되는 방식을 정의할 수 있습니다. 다음 두 가지 방법으로 서로 다른 실행 모드를 정의할 수 있습니다.
        1. manifest 파일 사용 : manifest 파일에서 액티비티를 선언하면 액티비티가 시작될 때 작업과 연결되어야 하는 방식을 지정할 수 있습니다.
        2. 인텐트 플래그 사용
            1. startActivity()를 호출할 때 새 액티비티가 현재 작업과 연결되어야 하는 방식(또는 연결되어야 하는지 여부)을 선언하는 플래그를 Intent에 포함할 수 있스브니다.
    2. 두 액티비티가 모두 액티비티 B가 작업과 연결되어야 하는 방식을 정의하면 액티비티 A의 요청(인텐트에 정의)이 액티비티 B의 요청(manifest에 정의) 보다 우선합니다.
    3. manifest 파일 사용
        1. manifest 파일에서 액티비티를 선언할 때 < activity> 요소의 launchMode 속성을 사용하여 액티비키가 작업과 연결되어야 하는 방식을 지정할 수 있다.
        2. standard(기본 모드)
            1. 기본값
            2. 시스템은 액티비티가 시작된 작업에 액티비티의 새 인스턴스를 생성하고 인텐트를 인스턴스로 라우팅합니다.
        3. singleTop
            1. 작업의 백 스택이 A-B-C-D이며 D가 맨 위에 있다고 하자
            2. D에 standard 실행모드가 있으면 클래스의 새 인스턴스 위에 실행되고 A-B-C-D-D가 된다.
            2. 하지만 D의 실행모드가 singleTop이면 D의 기존 인스턴스는 onNewIntent()를 통해 도착한 인텐트를 받는다.
            3. D의 기존 인스턴스가 스택의 맨 위에 있기 때문에 스택은 계속 A-B-C-D로 유지된다.
            4. 그러나 B유형의 액티비티의 인텐트가 도착하면 B의 새 인스턴스가 스택에 추가되며 B의 실행 모드가 singleTop이더라도 그렇다.
        4. simgleTask
            1. 시스템이 새 작업을 생성하고 새 작업의 루프에 있는 액티비티를 인스턴스화한다. 그러나 액티비티의 인스턴스가 이미 별도의 작업에 있다면 시스템은 새 인스턴스를 생성하지 않고 onNewIntent()메서드를 호출하여 인텐트를 기존 인스턴스로 라우팅한다.
            2. 액티비티의 인스턴스가 한번에 하나만 존재할 수 있다.
        5. sinleInstance
            1. singleTask와 동일하지만 시스템이 인스턴스를 보유한 작업으로는 어떤 다른 액티비티도 실행하지 않는다는 점이 다르다.