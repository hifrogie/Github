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
2. LinearLayout
    1. 여러 View 위젯들을 가로/세로 방향으로 나열할 때 사용하는 Layout
    2. orientation속성을 가지고 있어 가로,세로를 설정할 수 있다.
    3. 자식들은 중첩되지 않고 지정한 방향으로 쌓이는 형태로 표시된다.
    4. weight 속성으로 가중치를 설정할 수 있다 비율로 나타낼 수 있다. 다양한 디바이스 화면에 dp가 아니라 비율에 따른 대응으론 좋다.
3. ConstraintLayout
    1. 레이아웃에 배치되는 뷰들에 여러 제약을 적용하여 각 뷰의 위치와 크기를 결정하는 레이아웃
    2. RelativeLayout의 상대적 위치 관계에 따른 배치 + LinearLayout의 가중치가 가진 장점 + chain 사용으로 다른 레이아웃 없이 요소들을 그룹화

### 3. 왜 ConstraintLayout을 써야할까?
1. onMeasure() 호출 개수를 가지고서 레이아웃 성능 비교를 하고 있다.
2. onMeasure()메서드는 뷰의 크기를 구하는 역할을 하게 됨
![이미지1](https://velog.velcdn.com/images%2Fjaeyunn_15%2Fpost%2Fbcc1423e-b591-451b-a0a1-f58f131c1a2e%2Fimage.png)

![이미지2](https://velog.velcdn.com/images%2Fjaeyunn_15%2Fpost%2F18a40f93-807a-434d-9650-58534819b048%2Fimage.png)

![이미지3](https://velog.velcdn.com/images%2Fjaeyunn_15%2Fpost%2Fa206d9f6-e41d-4819-a467-03a7e49b03da%2Fimage.png)