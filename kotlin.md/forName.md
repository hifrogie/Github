## 19. Class.forName()
### 1. 정의
1. 로딩하고자 하는 클래스 명으로 클래스를 찾아 로드한다.
2. Class.forName(String name, boolean initialize, ClassLoader loader)
    1. name 
        1. 완전 정규화된 클래스 명
    2. initialize 
        1. 클래스 안에 static을 초기화 할지 설정
        2. 기본값 true
    3. loader 
        1. 클래스 로더를 지정
            1. 클래스 로더 : 런타임에 클래스를 로드하는 것
        2. 기본값 loader = this.getClass().getClassLoader()

### 2. 메소드 
1. newInstance()
    1. 새로운 메서드를 추가한다.