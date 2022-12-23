## 13.기본 정렬 알고리즘
### 1. 버블 정렬(Bubble Sort)
1. 서로 인접해 있는 요소 간의 대소 비교를 통해 정렬한다.
2. 시간 복잡도 : O(n²)
3. 공간 복잡도 
    1. 최선 : O(1)
    2. 최악 : O(n) (하나의 배열만 사용하기 때문)
4. 배열을 순차 탐색하여 i,i+1번째 요소를 비교하여 큰 것을 뒤로 이동. 이 과정이 1번 처리되는 경우 가장 큰 수가 배열 마지막에 위치 함 다음 탐색 부터는 마지막 요소는 안해도 됨
5. 장점
    1. 구현이 쉽고 코드가 직관적이다.
    2. n개의 원소에 대해 n개의 메모리를 사용하기에 데이터를 하나씩 정밀 비교가 가능하다.
6. 단점
    1. 최선이든 최악이든 O(N²)이라는 시간 복잡도를 갖는다.
    2. n개의 원소에 대해 n개의 메모리를 사용하기에 원소의 개수가 많아지면 비교 횟수가 많아져 성능이 저하된다.

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
4. 공간 복잡도
    1. 최선 : O(1)
    2. 최악 : O(n)
5. 장점 
    1. 알고리즘이 단순하다.
    2. 원소가 정렬되어 있는 경우 효율적이다.
    3. 제자리 정렬이므로 다른 메모리 공간을 필요로 하지 않는다.
    4. 버블 정렬과 선택 정렬에 비래 빠르다.
6. 단점 
    1. 시간 복잡도가 최악이다.
    2. 배열의 길이가 길어질수록 비효율적이다.

![삽입 정렬](https://blog.kakaocdn.net/dn/SHuOF/btrJA4MAAQL/odyyoSURJ7MFJlcOsk1Z61/img.gif)

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

### 3. 선택 정렬(Selection Sort)
1. 배열에서 최소값을 반복적으로 찾아 정렬하는 알고리즘
2. 정렬 여부와 관계없이 모든 경우의 수를 전부 확인한다.
3. 첫번째는 주어진 배열에서 최소값을 찾는다 두번쨰는 최소값을 맨 앞의 값과 바꾼다. 세번쨰는 바꿔준 맨 앞 값을 제외한 나머지 원소를 동일한 방법으로 바꿔준다.
4. 선택 정렬은 크게 2가지로 최소 선택 정렬과 최대 선택 정렬이 있다. 최소는 위와 같이 오름차순으로 정렬하는 것이고 최대는 내림차순으로 정렬하는 것이다.
5. 시간 복잡도 : O(n²)
6. 공간 복잡도 
    1. 최선 : O(1)
    2. 최악 : O(n)
7. 장점 
    1. 알고리즘이 단순하다.
    2. 실제로 교환하는 횟수가 적기 때문에 많은 교환이 일어나야하는 자료상태에서 효율적이다.
    3. 배열 안에서 교환하는 방식이므로 다른 메모리 공간을 필요로 하지 않는다.
8. 단점
    1. 시간 복잡도가 제곱이므로 비효율적이다.

![선택 정렬](https://blog.kakaocdn.net/dn/bb8tQu/btrJU0B7qfY/WUZh6MNJtJqkdWdKl1ncK0/img.gif)

```java
void selectionSort(int[] arr) {
    int indexMin, temp;
    for (int i = 0; i < arr.length-1; i++) {        // 1.
        indexMin = i;
        for (int j = i + 1; j < arr.length; j++) {  // 2.
            if (arr[j] < arr[indexMin]) {           // 3.
                indexMin = j;
            }
        }
        // 4. swap(arr[indexMin], arr[i])
        temp = arr[indexMin];
        arr[indexMin] = arr[i];
        arr[i] = temp;
  }
  System.out.println(Arrays.toString(arr));
}
```

### 4. 퀵 정렬(Quick Sort)
1. 퀵 정렬은 분할정복법과 재귀를 사용해 정렬하는 알고리즘이다.
2. 파이썬이나 자바에서 언어에서 자체 내장되어있는 정렬 알고리즘도 퀵 정렬을 기반으로 한다.
3. 퀵 정렬에는 피봇(pivot)이라는 개념이 사용된다. 피봇은 정렬될 기준 원소를 뜻한다.
4. 피봇의 선택 방법에 따라 퀵 정렬의 성능이 달라질 수 있다.최적의 피봇 선택이 어려우므로 임의 선택을 해야 한다. 보통 배열의 첫번째 값이나 중앙 값을 선택한다. 
5. 퀵 정렬의 동작 방식
    1. 예를 들어 배열 [ 5,6,1,4,2,3,7]이 있고 피봇을 임의로 4를 선택했다 가정 하자 4를 기준으로 작은 것은 왼쪽으로 큰 것은 오른쪽으로 보내 [ 1,2,3] < 4 < [ 5,6,7]를 생성한다.
    2. 다시 왼쪽에서부터 임의의 피봇 2를 설정하여 [ 1]< 2 < [ 3]을 생성하고 오른쪾에선 임의의 피봇 6을 설정하여 [ 5]< 6 < [ 7]로 나눈다.
    3. 배열 길이가 1이 된다면 정렬 완료 된 것이므로 분할된 배열을 합쳐 줌으로써 정렬을 마친다.
6. 퀵 정렬 시간 복잡도 
    1. N = 2^k개의 원소를 정렬한다고 가정할 때
        - O(Nlog₂N)
    2. 배열이 이미 정렬 되어 있는 경우
        - O(n²)
7. 공간 복잡도
    1. 최선 : O(1)
    2. 최악: 주어진 배열 안에서 교환을 통해 정렬이 수행 되므로 O(n)
8. 장점
    1. 속도가 빠르다.
    2. 가장 빠른 정렬 알고리즘
    3. 추가 메모리 공간이 필요하진 않다.
9. 단점 
    1. 정렬된 리스트에서는 오히려 시간이 많이 걸림

![퀵 정렬](https://blog.kakaocdn.net/dn/b1MCpR/btrJ2oQcWGj/bwBvSqcMMSTNpXQh2NGFMK/img.gif)

```java
public class QuickSorter {
    public static List<Integer> quickSort(List<Integer> list) {
        if (list.size() <= 1) return list;
        int pivot = list.get(list.size() / 2);

        List<Integer> lesserArr = new LinkedList<>();
        List<Integer> equalArr = new LinkedList<>();
        List<Integer> greaterArr = new LinkedList<>();

        for (int num : list) {
            if (num < pivot) lesserArr.add(num);
            else if (num > pivot) greaterArr.add(num);
            else equalArr.add(num);
        }

        return Stream.of(quickSort(lesserArr), equalArr, quickSort(greaterArr))
                .flatMap(Collection::stream)
                .collect(Collectors.toList());
    }
}
```

### 5. 병합 정렬(Merge Sort)
1. 분할 정복과 재귀 알고리즘을 사용하는 정렬 알고리즘이다.
2. 퀵 정렬과 함께 두 알고리즘이 사용된다는 측면에서 공통점을 가진다.
3. 차이점은 퀵 정렬이 피봇 선택 이후 피봇 기준으로 대소를 비교하는 반면 병합 정렬은 배열을 원소가 하나만 남을 때 까지 이분할 한다음 대소관계를 고려하여 다시 재배열하며 원래 크기의 배열로 병합한다.
4. 작동방식 
    1. 예를 들어 배열 [ 6,5,1,4,3,2,8,7]이 있을 때, 첫번째로 [ 6,5,1,4]와 [ 3,2,8,7]로 분리한다.
    2. 두번째로 [ 6,5],[ 1,4],[ 3,2],[ 8,7]로 나눈다.
    3. 세번째로 [ 6],[ 5],[ 1],[ 4],[ 3],[ 2],[ 8],[ 7]로 나눈다.
    4. 이렇게 모든 원소가 분리되면 대소 관계를 고려하여 병합과정을 거친다.
    5. 첫번째로 [ 5,6],[ 1,4],[ 2,3],[ 7,8]
    6. 두번쨰로 [ 1,4,5,6],[ 2,3,7,8]
    7. 마지막으로 [ 1,2,3,4,5,6,7,8]과 같이 정렬이 완료되며 알고리즘이 종료된다.
5. 시간 복잡도 : O(nlogn)
6. 공간 복잡도 
    1. 최선 : O(1)
    2. 최악 : O(nlogn)
7. 장점
    1. 퀵 정렬과 달리 기준값을 설정하는 과정없이 무조건 절반으로 분할하기에 기준값에 따라 성능이 달라지는 경우가 없다.
8. 단점
    1. 병합 정렬은 임시 배열에 원본맵을 계속해서 옮겨주며 정렬을 하는 방식이기에 추가적인 메모리가 필요하다.
    3. 퀵정렬 보다 병합 정렬이 빠르짐나 추가 메모리를 감당할 수 없다면 퀵을 사용해야한다.

![병합 정렬](https://blog.kakaocdn.net/dn/cGGmSI/btrJ70BiCLE/rqEPArt3AJMpp9u0tKsnL0/img.gif)
```java
public class Main {

    public static int[] src;
    public static int[] tmp;
    public static void main(String[] args) {
        src = new int[]{1, 9, 8, 5, 4, 2, 3, 7, 6};
        tmp = new int[src.length];
        printArray(src);
        mergeSort(0, src.length-1);
        printArray(src);
    }

    public static void mergeSort(int start, int end) {
        if (start<end) {
            int mid = (start+end) / 2;
            mergeSort(start, mid);
            mergeSort(mid+1, end);

            int p = start;
            int q = mid + 1;
            int idx = p;

            while (p<=mid || q<=end) {
                if (q>end || (p<=mid && src[p]<src[q])) {
                    tmp[idx++] = src[p++];
                } else {
                    tmp[idx++] = src[q++];
                }
            }

            for (int i=start;i<=end;i++) {
                src[i]=tmp[i];
            }
        }
    }

    public static void printArray(int[] a) {
        for (int i=0;i<a.length;i++)
            System.out.print(a[i]+" ");
        System.out.println();
    }
}
```

### 6.힙 정렬(Heap Sort)
1. 힙이란 트리 기반의 자료구조로서, 두 개의 노드를 가진 완전 이진 트리를 의미한다. 따라서 힙 정렬이란 완전 이진 트리를 기반으로 하는 정렬 알고리즘이다.
2. 힙의 분류는 크게 최대 힙과 최소 힙 두가지로 나뉜다. 최대 힙은 내림차순 정렬에 사용하며 최소 힙은 오름차순 정렬에 사용한다.

![힙 정렬](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F9l1Zq%2FbtrKoUPIC6s%2FqhwJBKLBr9CPQx6ttSJJQ1%2Fimg.png)

3. 최대 힙의 경우 부모노드는 항상 자식 노드 보다 크다는 특징을 가진다. 반대로 최소 힙의 경우 부모 노드가 항상 자식 노드보다 작다는 특징을 가진다.
4. 힙은 정렬된 구조가 아니다. 부모 자식 간의 대소관계만 나타내며 좌우 관계는 나타내지 않기 때문이다. 
5. 예를 들어 최소 힙에서 대부분 왼쪽 노드가 오른쪽 노드보다 작지만 4의 자식 노드는 7과 5는 왼쪽이 오른쪽 보다 크다.
6. 힙은 완전 이진 트리기 때문에 적절히 중간 레벨의 노드를 추출하면 중값에 가까운 값을 근사치로 빠르게 추출할 수 있다는 장점을 가지고 있다.
7. 때문에 힘은 배열에 순서대로 표현하기에 적합하다.
8. 또한 균형을 유지하려는 특징 때문에 힙은 우선순위 큐, 다 익스트라, 힙 정렬, 프림 알고리즘에 활용된다. 특히 힙 덕분에 다 익스트라 알고리즘의 시간 복잡도는 O(V²)에서 O(ElogV)로 줄어들수 있었다.
9. 시간 복잡도 : O(NlogN)
10. 공간 복잡도 
    1. 최선 : O(1)
    2. 최악 : O(nlogn)
11. 장점
    1. 추가적인 메모리를 필요로 하지 않으며 항상 O(nlogn)의 시간 복잡도를 갖는다.
    2. O(nlogn)인 정렬 방법 중 가장 효율적인 정렬방법이다. 퀵 정렬의 경우 효율적이나 최악의 경우 시간이 오래 걸린다는 단점이 있으나 힘 정렬의경우 항상 같은 시간 복잡도가 보장된다.
12. 단점
    1. 이상적인 경우에 퀵 정렬과 비교했을 때 똑같이 O(NlogN)이 나오긴 하나 실제 시간을 측정하면 퀵 정렬보다 느리다. 
    2. 즉 데이터의 상태에 따라서 다른 정렬들에 비해서 조금 느린 편이고 안정성을 보장받지 못한다.

```java
import java.util.PriorityQueue;
 
public class test {
	public static void main(String[] args) {
    
		int[] arr = {3, 7, 5, 4, 2, 8};
		System.out.print(" 정렬 전 original 배열 : ");
		for(int val : arr) {
			System.out.print(val + " ");
		}
		
		PriorityQueue<Integer> heap = new PriorityQueue<Integer>();
		
		// 배열을 힙으로 만든다.
		for(int i = 0; i < arr.length; i++) {
			heap.add(arr[i]);
		}
		
		// 힙에서 우선순위가 가장 높은 원소(root노드)를 하나씩 뽑는다.
		for(int i = 0; i < arr.length; i++) {
			arr[i] = heap.poll();
		}
		
		
		System.out.print("\n 정렬 후 배열 : ");
		for(int val : arr) {
			System.out.print(val + " ");
		}
		
	}
}
```

### 7. 셀 정렬(Shell Sort)
1. 셀 정렬이란 삽입 정렬의 단점을 보완하고자 도입되었다.
2. 삽입 정렬은 주어진 정렬 상태가 역순으로 배열되어 있을수록 비교 횟수가 늘어나고 최선의 경우 O(N)이지만 최악의 경우 O(N²)으로 성능 차이가 크다.
3. 셀 정렬은 이러한 시간복잡도를 평균적으로 O(N^1.25) 또는 O(N^1.5)수준으로 낮추고자 도입된 알고리즘이다. 
4. 셀 정렬의 핵심 개념은 interval(간격)이다.
5. interval은 비교할 원소 간의 간격을 의미한다. 셀 정렬에서는 비교 횟수를 줄이기 위해 interval은 큰 값에서 낮은 값으로 낮춰간다.
6. 동작 방식
    1. 배열에서 interval 만큼 떨어진 원소들을 부분 집합으로 구성한 뒤 삽입 정렬을 진행하는 방식으로 진행된다.
    2. 초기 interval 값은 len(array)/2로 설정하며 계속 2로 나누어준다.
    3. 예를 들어 아래와 같이 배열의 크기가 8이라면 초기 interval = 4가 되어 아래와 같이 비교가 진행 된다.

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbBVl5o%2FbtrK8gXmTC9%2FU1KRo46fkxklOQRADxzsM0%2Fimg.jpg)

    4. interval이 4인 경우 거리가 4만큼 떨어져 있는 원소끼리 부분집합을 이루어 비교대상이 된다.
    5. 위 그림에선 (35,14),(33,19),(42,27),(10,44)가 서로 비교 대상이 된다.
    6. 비교 진행한 뒤 interval을 2로 나누어주어 4에서 2가 된다.
    7. 이후 다시 interval 만큼 떨어진 원소를 부분 집합화하여 비교한다.
    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F6nxUK%2FbtrK4Dfx680%2Fngu9sPs6EUMs5ZdER3CsT1%2Fimg.jpg)
    8. interval이 2인 경우 거리가 2만큼 떨어져있는 원소끼리 부분 집합을 이뤄 비교한다.
    9. (14,27,35,42),(19,10,33,34)가 부분집합이 되어 정렬이 진행된다.
    10. 이후 다시 interval을 2로 나눠주어 1이 되면 아래와 같이 삽입 정렬이 진행된다.

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FzUjRd%2FbtrK56ujE0u%2Fh1hHntDAf0CFZ6eyd2u6P1%2Fimg.jpg)

7. 시간 복잡도
    1. 최선 : O(n)
    2. 평균 : O(n^1.5)
    3. 최악 : O(n²)
8. 공간 복잡도
    1. 최선 : O(1)
    2. 최악 : O(n)
9. 장점
    1. 삽입 정렬에 비해 성능이 우수하다.
    2. 어떤 데이터가 제 위치에서 멀리 떨어져있을 경우 여러번의 교환이 발생하는 버블 정렬의 단점을 해결한다.
10. 단점
    1. 일정한 간격에 따라 배열을 보아야 하며 간격을 잘못 설정할 경우 성능이 급격히 저하될 수 있다.

```java
package shellsort; 

public class ShellSort_v1 { 
	static void shellSort(int[] a, int n) { 
    	for (int h = n / 2; h > 0; h /= 2) {
        	for (int i = h; i < n; i++) {
				 int j; int temp = a[i]; 
                 for (j = i - h; j >= 0 && a[j] > temp; j -= h) { // 떨어져있는 만큼 이동하여 교환
                	 a[j + h] = a[j]; } a[j + h] = temp;
                 }
         }
    } 
}
```

### 8. 기수 정렬 (Radix Sort)
1. 기수 정렬은 non-comparison 알고리즘으로 원소간의 대소 비교를 하지 않고 정렬하는 알고리즘이다. 
2. 대신 기수 정렬은 정렬하고자 하는 수의 낮은 자리 수를 차례대로 확인하여 정렬하는 방식
3. 정렬을 위해 총 10개의 queue를 사용한다.

![이미지](https://blog.kakaocdn.net/dn/dUp4gV/btrK5DTSbpv/JadTLyrAgeExyGGS6mymo0/img.gif)

4. 동작 원리
    1. 첫번째로 1의 자리 수를 확인하여 각 원소의 1의 자리에 해당하는 queue에 쌓아준다. 이후 0~9의 queue를 순회하여 차례대로 가져온다.
    2. 두번째로 10의 자리 수를 확인하여 각 원소의 10의 자리에 해당하는 queue에 쌓아준다. 이후 0~9의 queue를 순회하여 차례대로 가져온다.
    3. 세번째가 진행되기 위해서는 100의 자리 수를 가진 값이 있어야 하며 n번째가 진행되기 위해서는 10^(n-1)의 자리 수를 가진 수가 있어야 한다.
5. 시간 복잡도
    1. O(n)
    2. 데이터의 개수가 n이고 데이터의 최대 자리수가 k라고 했을 때 n*k번 연산을 하기 때문에
6. 공간 복잡도 
    1. O(n+k)

```java
package Algorithm;

import java.util.Arrays;
import java.util.Random;

public class RadixSort {

    static final int N = 10;

    public static void main(String[] args) {
        Random random = new Random(); // 랜덤함수를 이용

        int[] arr = new int[N];
        for (int i = 0; i < N; i++) {
            arr[i] = random.nextInt(100); // 0 ~ 99
        }

        System.out.println("정렬 전: " + Arrays.toString(arr));
        radixSort(arr);
        System.out.println("정렬 후: " + Arrays.toString(arr));
    }

    private static void radixSort(int[] arr) {
        // 최대값 구하기
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (max < arr[i])
                max = arr[i];
        }

        // Counting Sort를 사용하여 해당 자리 정렬하기.
        for (int digit = 1; digit <= max; digit *= 10) {
            countingSort(arr, digit);
        }
    }

    private static void countingSort(int[] arr, int digit) {
        int[] temp = new int[N]; // 임시로 사용할 공간
        int[] counting = new int[10]; // 카운팅 배열

        for (int i = 0; i < N; i++) {
            int num = (arr[i] / digit) % 10; // 해당 자리수의 숫자 추출
            counting[num]++;
        }

        // 누적합 배열로 만들기
        for (int i = 1; i < counting.length; i++) {
            counting[i] += counting[i - 1];
        }

        // 뒤에서 부터 시작 >> 값이 큰것이 뒤로 가야하기 때문
        for (int i = 0; i < N; i++) {
            int num = (arr[i] / digit) % 10;
            int index = counting[num];

            temp[index - 1] = arr[i];
            counting[num]--;
        }

        // 복사
        for (int i = 0; i < N; i++) {
            arr[i] = temp[i];
        }
    }

}
```

### 9. 카운팅 정렬(Counting Sort)
1. 카운팅 정렬(계수 정렬)은 non-comparison sort 알고리즘에 해당하는 알고리즘으로 comparison sort에 해당하는 버블, 선택, 힙, 병합, 퀵, 삽입이 평균적으로 O(nlogn)이나 O(n²)의 시간 복잡도를 갖기에 이를 O(n)수준으로 낮추고자 도입된 알고리즘이다.
2. 카운팅 정렬의 동작은 이름 그대로 배열에 존재하는 원소 별 개수를 세어 정렬하는 방식이다.

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FtKb5x%2FbtqEvhaLlLz%2FqSnkDsN5JB4KY8rQPhqRek%2Fimg.png)
3. 동작 과정
    1. array를 한 번 순회하면서 각 값이 나올때 마다 해당 값을 index로 하는 새로운 배열의 값을 index로 하는 새로운 배열(counting)의 값을 1 증가시킨다.
    2. array[ 0] = 7 이므로 counting[ 7] 값을 1 증가
    3. array[ 1] = 2 이므로 counting[ 2] 값을 1 증가
    4. 이 과정을 마치면 다음 그림 처럼 된다.

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FM2d0N%2FbtqEuzQKkA3%2Fkc1r9KKWnW1x7RcelhfFK0%2Fimg.png)

    5. counting 배열은 각 값의 개수가 담겨있는 배열이 된다.
    6. counting 배열의 각 값을 누적 합으로 변환시킨다.

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmuC6D%2FbtqEtuiBgMx%2FGjorpguRqRsgvsklwgLZx0%2Fimg.png)

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FNaJnl%2FbtqEtuiBnYn%2FL8LK2XYYKu8PhYr0nmZpK0%2Fimg.png)

    7. 정렬을 할 경우 counting 배열의 각 값은 (시작점 - 1)을 알려준다. 즉 해당 값에 대응 되는 위치에 배정하면 된다는 의미
    8. array[ 0]=7이고, counting[ 7]=12 이다. 여기서 counting[ 7]의 값에 1을 뺴준 뒤 해당 값이 새로운 배열의 인덱스 11에 위치하게 된다.
    9. array[ 1] = 2 이고, counting[ 2] = 4 이다. 여기서 counting[ 2] 의 값에 1 을 빼준 뒤 해당 값이 새로운 배열의 인덱스 3에 위치하게 된다.
    10. 안정적으로 정렬하기 위해서 array의 마지막 index 부터 순회하는 것이 좋다.

    ![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FKBSml%2FbtqEvhosPPX%2FL70xRWd3gdGz9qXSBmiAN1%2Fimg.png)
4. 시간 복잡도
    1. O(n+k)
    2. k = o(n) 이면 O(n)
5. 공간 복잡도
    1. k =  배열에서 등장하는 최대값
    2. O(k)
6. 장점
    1. 매우 빠르다
7. 단점
    2. 데이터의 범위가 크면 만들어야하는 배열의 크기가 크므로 메모리의 낭비가 심하다.

```java
import java.util.Arrays;
import java.util.Collections;
public class CountingSort {
    public static void main(String[] args) {
        Integer[] a = {1, 0, 3, 1, 3, 1};
        a = sort(a);
        System.out.println(Arrays.toString(a));
    }
    public static Integer[] sort(Integer[] a) {
        int max = Collections.max(Arrays.asList(a));
        Integer[] aux = new Integer[a.length];
        Integer[] c = new Integer[max+1];
        Arrays.fill(c, 0);
        // 각 원소 갯수 계산
        for (int i=0; i<a.length; i++) {
            c[a[i]] += 1;
        }
        // 누적합 계산
        for (int i=1; i<c.length; i++) {
            c[i] += c[i-1];
        }
        // 누적합을 이용해 정렬
        for (int i=a.length-1; i>=0; i--) {
            aux[--c[a[i]]] = a[i];
        }
        return aux;
    }
}
```
