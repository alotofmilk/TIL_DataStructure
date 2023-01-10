# 🛒 **Priority Queue**

> **우선순위가 가장 높은** 데이터를 **가장 먼저 삭제**하는 자료구조

데이터를 우선순위에 따라 처리하고 싶을 때 사용한다. 물건을 모아두었다가 가장 가치가 높은 물건부터 꺼내어 확인하는 경우를 떠올리면 편하다!

### **구현 방법**

- 리스트를 이용하여 구현하기
- 힙(heap)을 이용하여 구현하기 ← 정렬이 용이함!

### **힙(Heap)의 특징**

- **완전 이진 트리**
- 항상 **루트 노드**를 **제거**
- 최소 힙 (min heap) ← 파이썬에서는 기본적으로 최소 힙을 지원한다!
- 최대 힙 (max heap)

### 완전 이진 트리

> **루트 노드부터** 시작하여 **왼쪽 자식 노드, 오른쪽 자식 노드 순서**로 **차례대로 삽입**되는 트리를 의미한다!

### 최소 힙 (min heap)

> **루트 노드**가 **가장 작은 값**을 가지는 구조

> 값이 **작은 데이터부터** 우선적으로 **제거**된다.

- 최소 힙 구성 함수 : **heapify()**
    - 상향식으로 움직인다. 부모 노드로 거슬러 올라가며, 부모보다 자신의 값이 더 작은 경우엔 위치를 교체한다.

### 최대 힙 (max heap)

> 루트 노드가 가장 큰 값을 가지는 구조

> 값이 **큰 데이터부터** 우선적으로 **제거**된다.

### heapq
> 파이썬에서 제공하는 **heap** 라이브러리

- 리스트를 마치 최소 힙처럼 다룰 수 있게 만들어준다! 원소를 추가하거나 삭제하고 싶다면 heapq 모듈의 함수를 호출할 때마다 리스트를 인자로 넘겨줘야한다.

`import heapq` : 모듈 임포트

`heapq.heapify(heap)` : 기존 리스트를 힙 구조로 바꾸기

`heapq.heappush(heap, value)` : 삽입

`heapq.heappop(heap)` : 최솟값 (최상단 노드) 얻기 ← 삭제하고 얻기

`heap[0]` : 삭제하지 않고 조회만 하기

#### max heap을 다루고 싶다면?

`heapq.heappush(heap, -value)` : 삽입

`-heapq.heappop(heap)` : 제거

### 힙 정렬 예시 코드

```python
import sys
import heapq
input = sys.stdin.readline()

def heapsort(iterable):
    h = []; result = []
    # 모든 원소를 차례대로 힙에 삽입
    for value in iterable:
        heapq.heappush(h,value)
    # 힙에 삽입된 모든 원소들을 차례대로 꺼내어 담기
    for i in range(len(h)):
        result.append(heapq.heappop(h))
    return result

n = int(input())
arr = []

for i in range(n):
    arr.append(int(input()))

res = heapsort(arr)

for i in range(n):
    print(res[i])
```