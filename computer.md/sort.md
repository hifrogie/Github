## 13.기본 정렬 알고리즘
### 1. 버블 정렬(Bubble Sort)
1. 서로 인접해 있는 요소 간의 대소 비교를 통해 정렬한다.
2. 시간 복잡도 : O(n²)
3. 공간 복잡도 : O(n) (하나의 배열만 사용하기 때문)
4. 배열을 순차 탐색하여 i,i+1번째 요소를 비교하여 큰 것을 뒤로 이동. 이 과정이 1번 처리되는 경우 가장 큰 수가 배열 마지막에 위치 함 다음 탐색 부터는 마지막 요소는 안해도 됨

![버블 이미지](https://blog.kakaocdn.net/dn/c4wQHp/btrJFPfz5sX/cztROqayVs8n8MRWJLdRX1/img.gif)

```java
public static void bubleSort(int[] arr) {
    for(int i = 0; i < arr.length; i++) {
        for(int j = 0 ; j < arr.length - i - 1 ; j++) {
            if(arr[j] > arr[j+1]) {
                int temp = arr[j+1];
                arr[j+1] = arr[j];
                arr[j] = temp;
            }
        }
    }
}
```

### 2. 삽입 정렬(Insert Sort)
1. 정렬을 진행 할 원소의 index보다 낮은 곳에 있는 원소들을 탐색하여 알맞은 위치에 삽입해주는 정렬 알고리즘이다.
2. 동작 방식
    1. 2번째 index 부터 시작한다. 첫번쨰 index는 비교할 원소가 없기 때문이다.
    2. 알고리즘이 동작하는 동안 계속해서 정렬이 진행되므로 반드시 맨 왼쪽 index까지 탐색하지 않아도 된다는 장점이 있다.
3. 시간 복잡도
    1. 데이터가 이미 정렬된 케이스 : O(N)
        - 버블 정렬 선택 정렬과 다르게 삽입 정렬은 break키워드가 존재한다.
        - 이미 정렬된 상태라면 정렬하려는 원소의 바로 앞 원소와 비교시 break 키워드를 통해 즉시 for문을 탈출한다.
    2. 데이터가 역순으로 정렬되어있는 케이스 : O(N²)
        - 매 사이클 마다 첫번째 원소 까지 방문해서 데이터의 위치를 변경해야 한다.

```java
//배열로 구현하는 경우
public static void insertSort(int[] arr) {
    for(int i = 1; i < arr.length; i++) {
        for(int j = i; j > 0; j--) {
            if(arr[j-1] > arr[j]) {
                int temp = arr[j-1];
                arr[j-1] = arr[j];
                arr[j] = temp;
            }
        }
    }
}
```

```java
//리스트로 구현하는 경우
public static List<Integer> insertSort(List<Integer> input) {
    LinkedList<Integer> list = new LinkedList<Integer>(input);
 
    for(int i = 0 ; i < list.size() ; i++) {
        for(int j = i ; j < list.size() ; j++) {
            if(list.get(i) > list.get(j)) {
                Integer temp = list.remove(j);
                list.add(i, temp);
            }
        }
    }
    
    return list;
}
```

