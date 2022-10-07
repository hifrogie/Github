## 4. Layout을 파헤치자
### 1. Layout과 ViewGroup
1. Layout
    1. View 위젯들을 그룹화하여 배치하기 위한 용도로 사용되는 ViewGroup
2. ViewGroup
    1. 다른 View를 포함 할 수 있는 View
    2. 컨테이너 역할을 수행

### 2. RelativeLayout & LinearLayout & ConstraintLayout
1. RelativeLayout
    1. 자식 View 위젯들이 서로 간의 상대적 배치관계에 따라 화면에 표시될 위치가 결정되도록 만들어주는 Layout클래스
    2. 상대적인 배치 기준을 정하지 않는다면, 내부에 중첩되어 표시된다.
    3. 특정 위젯을 기준으로 배치하게 된다.
    4. 아무런 조작을 하지 않았을 때는 왼쪽 상단부터 위젯이 쌓이게 된다.
2. 
3. ConstraintLayout
    1. 레이아웃에 배치되는 뷰들에 여러 제약을 적용하여 각 뷰의 위치와 크기를 결정하는 레이아웃