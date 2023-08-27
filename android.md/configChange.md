## 11. 구성 변경 처리
### 1. android:configChanges
1. 특정 구성 변경 시 자동 액티비티 재생성을 방지할 수 있습니다.
2. Activity를 다시 만들면 전체 UI와 Activity에서 파생된 객체도 다시 만들어집니다.
3. 이런 상황을 피해야할 이유가 있을 수 있는데 이럴 때는 액티비티가 구성 변경 처리를 직접한다고 선언하여 시스템이 액티비티를 다시 시작하지 못하도록 할 수 있습니다.
4. 매니페스트에서 < activivty> 항목에서 android:configChanges를 추가한다.

```kotlin
 <activity
    android:name=".MyActivity"
    android:configChanges="orientation|screenSize|screenLayout|keyboardHidden"
    android:label="@string/app_name">
```
5. 액티비티와 모든 연결된 뷰는 Activity.onConfigurationChanged() 호출을 수신한다.
6. override fun onCofigurationChanged() 콜백 메서드는 새 기기 구성을 지정하는 Configuration 객체를 수신한다. 
7. Configuration 객체의 필드를 읽고 새 구성이 무엇인지 확인한다.
8. 이후에 변경하려면 인터페이스에서 사용하는 리소스를 업데이트하세요.
9. 시스템에서 이 메서드를 호출하면 액티비티의 Resources 객체가 새 구성에 따라 리소스를 반환하도록 업데이트 됩니다.
10. 이에 시스템에서 액티비티를 다시 시작하지 않고도 ui요소를 재설정할 수 있습니다.
11. 이 기법을 사용할 때도 일반 액티비티 수명 주기 동안 상태를 유지해야합니다.
12. 방지할 수 없는 구성변경은 앱을 다시 시작할 수 있습니다.
13. 프로세스를 종료처리할 수 있어야한다.