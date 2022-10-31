## 9. 트리
### 1. 트리란 무엇인가?
1. 트리 구조는 비선형(Non-linear)자료구 중 하나이다.
2. 비선형 자료구조에서는 하나의 자료 뒤에 여러개의 자료가 존재할 수 있기 때문에 폴더 구조와 같은 계층적 구조를 나타내기에 적절하다.

### 2. 트리 용어 정리

![이미지](https://oopy.lazyrockets.com/api/v2/notion/image?src=https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F96df8c7c-c204-4e1a-bcd7-581f37d62d4f%2FUntitled.png&blockId=64a0461d-4d77-4a4a-849e-d3d9922c1b8f)

|용어|의미|
|:-:|:-:|
|노드(node)|컴퓨터 과학에 쓰이는 기초적인 단위, 동그라미|
|간선(edge)|노드와 노드를 이어주는 선|
|레벨(level)|트리의 특정 깊이를 가지는 노드의 집합|
|루트 노드(root node)|트리의 가장 높은 곳에 위치한 노드|
|단말 노드(leaf node)|자식이 없는 노드|
|형제(sibling)|같은 부모 노드를 가진 노드|

- 노드의 깊이(depth):루트에서 어떤 노드에 도달하기 위해 거쳐야 하는 간선의 수
    - D의 깊이 :2
    - H의 깊이 :3
- 노드의 레벨(level):트리의 특정 깊이를 가지는 노드의 집합. 
    - A의 레벨 : 0
    - B,C의 레벨 : 1
- 트리의 높이(height):루트 노드에서 가장 깊숙히 있는 노드의 높이
    - 3

### 3. 이진 트리(binary tree)
1. 이진 트리란 모든 노드의 자식 노드가 최대 2개의 노드를 가지는 트리를 의미한다.

![이미지](https://oopy.lazyrockets.com/api/v2/notion/image?src=https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fa3262e28-0aff-4080-87e6-21f65d7c39f9%2FUntitled.png&blockId=41fe4c4b-1acb-48fd-af1a-41804b4c4422)

2. 이진 트리의 종류
    1. 포화 이진 트리(full binary tree)
        - 모든 레벨에서 노드들이 모두 채워진 트리
    2. 완전 이진 트리(complete binary tree)
        - 마지막 레벨을 제외하고 노드가 모두 채워진 트리
        - 마지막 레벨도 다 채워져 있을 수 있다.
    3. 편향 트리(Skewed binary tree)
        - 왼쪽 또는 오른쪽 서브트리만 가지는 트리
        - 최악의 경우에는 모든 노드를 탐색해야하므로 시간복잡도는 O(n)이 된다.
        - 이 처럼 균형이 깨진 트리에서 스스로 균형을 잡고 시간 복잡도를 O(log n)을 보장하기위해 "레드블랙트리"나 "AVL 트리"를 사용한다.
3. 이진 트리를 사용하는 이유
    1. 선형 구조와 달리 탐색과 삽입에서 연산 횟수를 대폭 줄일 수 있기 때문이다.
    2. 배열,연결리스트,스택,큐,데크(Deque)와 같은 선형 자료구조에서는 하나의 자료 뒤에 오직 하나의 자료만 존재한다.
    3. 그렇기 때문에 선형 자료구에서는 정렬이 되어있지 않은 상태에서 특정 값을 탐색할 때, 최악의 시간 복잡도는 맨 끝까지 탐색하는 경우이기 때문에 O(n)이 된다.
    4. 하지만 이진트리에서는 탐색하는데 최적의 시간 복잡도는 O(log n)이 된다.
    5. 이를 증명하면 다음과 같다

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F22149E4958537FEB15)

### 4. B- 트리
1. 보통 B 트리라고 하면 B- 트리를 의미한다.
2. B 트리는 트리 자료 구조의 일종으로 이진트리를 확장해 하나의 노드가 가질 수 있는 자식 노드의 최대 숫자가 2보다 큰 트리 구조이다.
3. B 트리의 특징
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FtxFtg%2FbtrBfY0XYJQ%2FfcSzMZkIiltKSKISSGds31%2Fimg.webp)
    1. 노드에는 2개 이상의 데이터(key)가 들어갈 수 있으며, 항상 정렬된 상태로 저장된다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcgHm9w%2FbtrBgdKjl4c%2Fqa3I1iSi7DhPLruKUcmVn0%2Fimg.webp)
    2. 내부 노드는 M/2 ~ M개의 자식을 가질 수 있다.
    3. 최대 M개의 자식을 가질 수 있는 B트리를 M차 B트리라고 한다.
    4. 첫 번째 그림은 3차 B트리를 나타낸다. 즉, 3차 B트리의 리프 노드를 제외한 내부 노드는 1개 ~ 3개의 자식을 가질 수 있다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FQjG5H%2FbtrBgpDJkg7%2FkX1lyLc9sDUjTRSG98A0Mk%2Fimg.webp)
    5. 특정 노드의 데이터(key)가 K개라면, 자식 노드의 개수는 K+1개여야 한다.
    6. 두 번째 그림을 보면 특정 노드의 데이터가 2개면 자식 노드는 3개이고 특정 노드의 데이터가 1개면 자식 노드는 2개이다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FJOl2D%2FbtrBfFAuAgh%2FyWN5ZSHC3nZb0ebKCHJh1k%2Fimg.webp)
    7. 특정 노드의 왼쪽 서브 트리는 특정 노드의 key보다 작은 값들로, 오른쪽 서브트리는 큰 값들로 구성된다.
    8. B-트리는 노드 내에 key값이 2개 이상 들어갈 수 있기 때문에 자식 노드를 가리키는 포인터의 개수는 key의 개수보다 1개 더 많다. 
    9. 노드 내에서 key가 a1, a2, a3... 등으로 존재한다면, a1 왼쪽 서브 트리는 a1보다 작아야 하고, a1과 a2 사이의 서브 트리는 a1보다는 크면서 a2보다는 작아야 한다
    10. 예를 들어 4번쨰 그림을 보자. 10의 왼쪽 서브 트리는 10보다 작은 값이 위치한다. (10, 21) 사이의 서브 트리는 10보다는 크지만 21보다는 작은 값들이 위치한다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FJOl2D%2FbtrBfFAuAgh%2FyWN5ZSHC3nZb0ebKCHJh1k%2Fimg.webp)
    11. 노드 내에 데이터는 floor(M/2)-1개부터 최대 M-1개까지 포함될 수 있다 ( floor : 내림 함수 Ex-floor(3.7) = 3 )
    12. 여기서 floor는 내림 함수이다. 예를 들어 floor(3.6)=3이다.
    13/ 3차 B트리는 노드 내에 0~2개의 데이터를 가질 수있다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FBVE0C%2FbtrBfY05W5E%2FRglzAA2qKUL65h73IQLoN0%2Fimg.webp)
    13. 모든 리프 노드들이 같은 레벨에 존재한다. 즉, 루트 노드에서 모든 리프 노드로 가는 경로의 길이가 같다.