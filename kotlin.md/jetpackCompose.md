## 18. jetpack compose 
### 1. jetpack compose 란?
1. native UI를 만드는 toolkit
2. 코틀린 API
3. xml layout과 layout Editor를 사용하지 않고 composable functions를 호출하여 정의할 수 있다.

### 2. tutorial
1. composable functions
    1. jetpack compose는 composable functions로 구성되어있다.
    2. composable functions을 만들려면 함수 이름에 @Composable 주석을 추가하기만 하면 된다.
2. 텍스트 요소 추가
    1. phone and tablet 카테고리에서 empty compose Activity 선택
    2. setContent{}는 composable function가 호출 가능한 액티비티의 레이아웃을 정의한다.
    3. jetpack compose는 kotlin 컴파일러 플러그인을 사용하여 composable function을 앱의 UI요소로 변환합니다.
    4. 예를 들어 compose UI 라이브러리에서 정의한 구성 가능한 Text 함수는 텍스트 라벨을 화면에 표시합니다.

    ```kotlin
    import android.os.Bundle
    import androidx.activity.ComponentActivity
    import androidx.activity.compose.setContent
    import androidx.compose.material.Text

    class MainActivity : ComponentActivity() {
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContent {
                Text("Hello world!")
        }
        }
    }
    ```
3. composable function 정의
    1. 함수를 구성 가능하게 하려면 @Composable 주석을 추가해야 합니다.

    ```kotlin
    import androidx.compose.runtime.Composable

    class MainActivity : ComponentActivity() {
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContent {
            MessageCard("Android")
            }
        }   
    }

    @Composable
        fun MessageCard(name: String) {
        Text(text = "Hello $name!")
    }
    ```

### 3. 장점
1. 코드 감소
    1. 테스트와 디버그 작업과 버그 발생 가능성이 줄어들어 문제에 집중할 수 있게 되며 관리자는 관리할 코드가 줄어든다.
2. 직관적
    1. Compose는 선언적 API를 사용한다. 
    2. Compose가 나머지를 처리하므로 UI를 설명하기만 하면 된다.
    3. API는 직관적임으로 찾아 쓰기 편하다.
3. 빠른 개발 과정
    1. 기존의 모든 코드와 호환된다. compose 에서 view를, views에서 compose를 호출 가능
    2. Navigation, ViewModel, Kotlin 코루틴 과 같은 일반적인 라이브러리는 Compose와 함께 작동하므로 언제 어디서든 원하는대로 채택할 수 있다.