## 2. OnClickListener()
### 1. xml layout에 직접 넣는 방법

```kotlin
<Button
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:onClick="onClick3"
    android:text="BTN 3" />
```

```kotlin
class MainActivity : AppCompatActivity() {
    private val TAG = MainActivity::class.java.simpleName
    .....

    public fun onClick3(v : View){
        Log.d(TAG,"clicked BTN_3")
    }
}
```

1. MainActivity::class.java.simpleName
    1. 코틀린에서 액티비티를 넘길 때 .java를 붙여 코드를 작성하는 것을 볼 수 있습니다.
    2. 그 이유는 자바에서 쓰는 클래스와 코틀린에서 쓰는 클래스가 다르기 때문입니다.
    3. 자바에서는 Class를 리턴하는 반면, 코틀린에서는 클래스명 ::class를 하게 되면 KClass를 리턴합니다.
    4. 그렇기 때문에 KClass를 Class로 바꿔줘야 하는데 이때 .java를 붙여 자바 클래스 값을 받습니다.

### 2. Activity에 interface 상속 받아서 사용할 경우

```kotlin
class MainActivity : AppCompatActivity() , View.OnClickListener {
    private val TAG = MainActivity::class.java.simpleName
    private lateinit var btn1 : Button
    private lateinit var btn2 : Button
    private lateinit var btn3 : Button

    override fun onCreate(savedInstanceState: Bundle?) {
        ......

        btn1 = findViewById(R.id.btn_1)
        btn2 = findViewById(R.id.btn_2)
        btn3 = findViewById(R.id.btn_3)

        btn1.setOnClickListener(this)
        btn2.setOnClickListener(this)
        btn3.setOnClickListener(this)

    }

    override fun onClick(v: View?) {
        when(v?.id){
            R.id.btn_1 -> {
                Log.d(TAG,"onClick() btn_1")
            }
            R.id.btn_2 -> {
                Log.d(TAG,"onClick() btn_2")
            }
            R.id.btn_3 -> {
                Log.d(TAG,"onClick() btn_3")
            }
            else -> {
                Log.d(TAG," onClick() invalid btn id")
            }
        }

    }
}
```

