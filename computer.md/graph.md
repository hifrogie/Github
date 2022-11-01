## 10. 그래프
### 1. 그래프란?
1. 그래프는 정점과 간선으로 이루어진 자료구조입니다.
2. 정확히는 정점(Vertex)간의 관계를 표현하는 조직도라고 볼수도 있겠습니다.
3. 그런면에서 트리는 그래프의 일종인 셈입니다.
4. 다만 트리와는 달리 그래프는 정점마다 간선이 없을 수도 있고 있을 수도 있으며 루트 노드, 부모와 자식이라는 개념이 존재하지 않습니다.
5. 또한 그래프는 네트워크 모델 즉, 객체와 이에 대한 관계를 나타내는 유연한 방식으로 이해할 수 있습니다.
6. 실생활에서 다양한 예를 그래프로 표현할 수 있습니다.
7. 지하철 노선도, 도심의 도로가 있습니다.
8. 이런 식으로 활용할 수 있는 방법이 많기에 문제도 다양하게 출제를 할 수 있습니다.
9. 그래프는 알고리즘에서 굉장히 많이 사용됩니다. 특히 그래프를 순회하는 방식인 DFS와 BFS를 잘 알아두어야 합니다.

### 2. 그래프에서 사용하는 용어
 ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcjbjPd%2FbtqKgF6OzSD%2FU0a7BKCpfJlhx1iJzwsEy1%2Fimg.png)

 1. 정점(vertice): 노드(Node)라고도 하며 정점에는 데이터가 저장됩니다.(0,1,2,3)
 2. 간선(edge):링크(arcs)라고도 하며 노드간의 관계를 나타냅니다.
 3. 인접 정점(adjacent vertex):간선에 의해 연결된 정점을 위에서 (정점 0과 정점1은 인접 정점)
 4. 단순 경로(simple-path):경로 중 반복되는 정점이 없는 것, 같은 간선을 지나가지 않는 경로
 5. 차수(degree):무방향 그래프에서 하나의 정점에 인접한 정점의 수(정점 0의 차수는 3)
 6. 진출 차수(out-degree):방향 그래프에서 사용되는 용어로 한 노드에서 외부로 향하는 간선의 수
 7. 진입 파수(in-degree):방향그래프에서 사용되는 용어로 외부 노드에서 들어오는 간선의 수

 ### 3. 그래프 구현 방법
 1. 그래프를 구현하는 방법에는 인접행렬(Adjacency Materix)와 인접 리스트(Adjacency List)방식이 있습니다.
 2. 두 개의 구현 방식은 각각의 상반된 장단점을 가지고 있는데 대부분 인접리스트 형식을 많이들 사용합니다.
 
 ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F7RFhy%2FbtqKkOhoYiE%2FSE3IQP2q0g3xd34EQZkjM1%2Fimg.png)
 
 3. 인접행렬 방식
    1. 인접 행렬은 그래프의 노드를 2차원 배열로 만든 것 입니다.
    2. 완성된 배열의 모양은 1,2,3,4,5,6의 정점을 연결하는 노드에 다른 노드들이 인접 정점이라면 1, 아니면 0을 넣어줍니다.
4. 인접행렬의 장점
    1. 2차원 배열 안에 모든 정점들의 간선 정보를 담기 때문에 배열의 위치를 확인하려면 두 점에 대한 연결 정보를 조회할때 O(1)의 시간 복잡도면 가능합니다.
    2. 구현이 비교적 간편합니다.
5. 인접행렬의 단점
    1. 모든 정점에 대해 간선 정보를 대입해야 하므로 O(n²)의 시간 복잡도가 소요됩니다.
    2. 무조건 2차원 배열이 필요하기에 필요 이상의 공간이 낭비됩니다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FNlh1G%2FbtqKicb2Wub%2FsHWVSS6bn2FZdijEJVR2r1%2Fimg.png)
6. 인접 리스트 방식
    1. 인접 리스트란 그래프의 노드들을 리스트로 표현한 것입니다. 주로 정점의 리스트 배열을 만들어 관계를 설정해줌으로써 구현합니다.
7. 인접리스트 장점
    1. 정점들의 연결 정보를 탐색할 때 O(n)시간이면 가능합니다. (n:간선의 갯수)
    2. 필요한 만큼의 공간만 사용하기 때문에 공간의 낭비가 적습니다.
8. 인접 리스트 단점
    1. 특정 두 점이 연결 되었는지 확인하려면 인접 행렬에 비해 시간이 오래 걸립니다.(배열보다 search 속도 느림)
    2. 구현이 비교적 어렵습ㄴ디ㅏ.

### 4. 다양한 그래프의 종류
![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F0ZsjG%2FbtqKjcbPzFp%2FEmai2Mc2IWMIAENKHr4Is1%2Fimg.png)
1. 무방향 그래프
    - 두 정점을 연결하는 간선에 방향이 없는 그래프 입니다.

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbvvxel%2FbtqKkPUXTtY%2FpsdErjeixg2KkpZWHc9NqK%2Fimg.png)
2. 방향 그래프
    - 방향 그래프는 두 정점을 연결하는 간선에 방향이 존재하는 그래프입니다.
    - 간선의 방향으로만 이동할 수 있습니다.

![가중치 그래프](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FBVFRy%2FbtqKopgFBy3%2FSlXKIsNr2avTAKIyLnwuvk%2Fimg.png)

3. 가중치 그래프
    - 두 정점을 이동할 때 비용이 드는 그래프

![완전그래프](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmPtuW%2FbtqKqyqTexj%2FUDBayShMmL3p8LGDl25uR1%2Fimg.png)

4. 완전 그래프
    - 완전 그래프는 모든 정점이 간선으로 연결되어 있는 그래프