## 7. 뷰가 화면에 그려지기까지 플로우
### 1. Layout이 그려지는 과정 설명
1. 안드로이드에서는 액티비티가 Focus를 얻게 되면 자신의 Layout을 그리게 됩니다.
2. 이때 그리고자 하는 Layout의 Root Node를 요청하게 되는데, 우리가 setContentView()를 호출할 때 Root Node가 정해집니다.
    - Root Node : 트리가 시각적으로 표현되는 방식에 따라 트리 데이터 구조의 맨위 또는 맨 아래 노드입니다. 루트 노드는 시각적 표현이 하향식이면 상단으로 간주되고 상향식이면 하단으로 간주 될 수 있습니다.
    - Child Node : 주어진 노드의 모든 하위 노드
3. Root Node를 따라 Child Node를 찾아가면서 차례대로 View를 그리게 됩니다.

### 2. Layout이 그려지는 과정
1. measure() -> onMeasure() -> layout() -> onLayout()
2. measure(widthMeasureSpec: Int, heightMeasureSpect: Int )
    - 뷰의 크기를 알아내기 위해 호출 되며, 실제 크기 측정을 위해 onMeasure()를 호출 합니다.
    - widthMeasrueSpec: Parent가 부여한 가로 공간
    - heightMeasureSpec: Parent가 부여한 세로 공간
3. onMeasure(widthMeasureSpec: Int, heightMeasureSpec: Int)
    - 실제 뷰의 크기를 측정합니다.
    - widthMeasureSpec : Parent가 부여한 가로 공간
    - heightMeasureSpec : Parent가 부여한 세로 공간
4. layout(left: Int, top: Int, right: Int, bottom: Int)
    - 뷰의 위치를 할당하기 위해 호출되며, 실제 할당을 위해 onLayout()을 호출합니다.
    - left : Parent에 대한 왼쪽 포지션
    - top : Parent에 대한 위쪽 포지션
    - right : Parent에 대한 오른쪽 포지션
    - bottom : Parent에 대한 하단 포지션
5. onLayout(changed: Boolean, left: Int, right: Int, bottom: Int)
    - 실제 뷰의 할당을 합니다.
    - changed: 새로운 사이즈나 위치인지 맞으면 true 아니면 false
    - left : Parent에 대한 왼쪽 포지션
    - top : Parent에 대한 위쪽 포지션
    - right : Parent에 대한 오른쪽 포지션
    - bottom : Parent에 대한 하단 포지션

### 3. Custom View LifeCycle
1. 뷰가 생성이 되면 다음 순서대로 메소드들이 호출이 됩니다.
2. View의 LifeCycle은 여러가지 이유로 공식적으로 제공이 되지 않습니다.
3. 아래 이미지는 널리 퍼져있는 View LifeCycle 입니다.

![이미지](https://miro.medium.com/max/692/1*abc0UlGj1myFD0eph4pZjQ.png)

4. Constructor
    - CustomView(context: Context) : 코드로 생성하면 호출
    - CustomView(context: Context, attributeSet: AttributeSet): xml로 생성하면 호출
5. onAttachedToWindow
    - Parent View가 addView(view: View)를 호출하면 해당 View가 window에 연결됩니다.
    - 이 단계 부터 id를 통해 접근할 수 있습니다.
    - window 
        - 뭔가를 그릴 수 있는 창
        - 보통 하나의 surface를 가지고 있으며, Application은 Window Manager와 상호작용하여 Window를 만듭니다. 
        - Window Manager는 각각의 Window 표면에 Component를 그리기 위해 Surface를 만듭니다.
        - Application은 surface에 원하는 것을 그릴 수 있습니다.
        - 일반적으로 Activity가 Window를 가지게 됩니다.
        - surface : 화면에 합성되는 픽셀을 보유한 객체
6. onMeasure
    - View의 사이즈 측정
    - MeasureSpec : Parent View에서 Child View로 요구 조건을 보내기 위해 사용
        - MesureSpec.EXACTLY : 직접적으로 width와 height에 대해 하드 코딩할 때
        - MeasureSpec.AT_MOST : Parent가 Child의 Maximum Size를 설정하기 위해 사용합니다.
        - MeasureSpec.UNSPECIFIED : Parent에 의해 사용되며 제한이 없기 때문에 Child View가 원하는 사이즈를 가질 수 있습니다.
7. onLayout
    - 개별 Child View들의 사이즈 및 위치 할당
8. onDraw
    - View 그리기 시작
    - Canvas와 Paint를 사용하여 그리기 시작하며 Canvas는 모양, Paint는 색을 칠합니다.
    - 리소스를 많이 사용하기 때문에 할당된 객체를 재사용할 수 있도록 해야합니다.
    - Canvas : 실제 UI를 그리기 위한 공간으로 비트맵이 그려지는 공간이라고 생각합니다.