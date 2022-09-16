## 9. 주생성자와 부생성자
### 1. 주생성자(primary constructor)

```
class User(val nickname: String)
```

```
class User constructor(_nickname: String){
    val nickname: String
    init{
        nickname = _nickname
    }
}
```

1. 클래스 이름 뒤에 오는 괄호로 둘러싸인 코드를 주생성자라고 부른다.
2. 주 생성자는 생성자 파라미터를 지정하고 그 생성자 파라미터에 의해 초기화되는 프로퍼티를 정의하는 두 가지 목적에 쓰인다. 
3. contructor 키워드는 주 생성자나 부 생성자 정의를 시작할 때 사용한다.
4. init 키워드는 초기화 블록을 시작한다.
5. 초기화 블록에는 클래스의 객체가 만들어질 때 실행될 초기화 코드가 들어간다.
6. 초기화 블록은 주 생성자와 함께 사용된다.
7. 주생성자는 제한적이기 때문에 별도의 코드를 포함할 수 없으므로 초기화 블록이 필요하다.
8. 클래스 안에 여러 초기화 블록을 선언할 수 있다.
9. 생성자 파라미터 _nickname에서 맨앞의 밑줄(_)은 프로퍼티와 생성자 파라미터를 구분해준다.

### 2. 부생성자(secondary)
```
class MyButton: View{
    constructor(ctx: Context) : super(ctx){}
    constructro(ctx: Context, attr: AttributeSet): super(ctx,attr){}
}
```

1. 생성자가 여럿 필요한 경우는 프레임 워크를 확장해야 하는데 여러 가지 방법으로 인스턴스를 초기화 할 수 있게 다양한 생성자를 지원해야하는 경우다.
2. 부생성자는 constructor 키워드로 시작한다.
3. 여기서 두 부 생성자는 super() 키워드를 통해 자신에 대응하는 상위 클래스 생성자를 호출한다.
4. 부생성자가 필요한 주된 이유는 자바 상호운용성이다.
5. 클래스 인스턴스를 생성할 때 파라미터 목록이 다른 생성 방법이 여럿 존재하는 경우에는 부 생성자를 여럿 둘 수 밖에 없다.