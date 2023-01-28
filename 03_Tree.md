# 🌳 **Tree**

> 가계도와 같이 **계층적인 구조를 표현**할 때 사용하는 자료구조

> 기본적으로 **트리의 크기가 N일 때, 전체 간선의 개수는 N-1**

- **루트 노드** (root node) : 부모가 없는 최상위 노드
- **단말 노드** (leaf node) : 자식이 없는 노드
- **크기** (size) : 트리에 포함된 모든 노드의 개수
- **깊이** (depth) : 루트 노드부터의 거리
- **높이** (height) : 깊이 중 최댓값
- **차수** (degree) : 각 노드의 자식 방향 간선 개수

### **이진 탐색 트리 (Binary Search Tree)** ###

> 이진 탐색이 동작할 수 있도록 고안된, 효율적인 탐색이 가능한 자료구조

- **왼쪽 자식 노드 < 부모 노드 < 오른쪽 자식 노드**
- 왼쪽 자식 노드는 부모 노드보다 작은 값을, 오른쪽 자식 노드는 큰 값을 갖는 구조

### 이진 탐색 트리 탐색 과정 ###
`1단계` **루트 노드 (최상위 노드) 부터 방문**하여 탐색을 진행한다.

`2단계` 찾고자 하는 값이 **루트 노드보다 작다면 왼쪽** 자식 노드들을, **루트 노드보다 크다면 오른쪽** 자식 노드들을 확인하면 된다. (모든 노드들을 탐색할 필요가 없어져 소요되는 시간이 크게 줄어든다는 장점이 있다.)

`3단계` 자식 노드들을 살펴보면서, 찾고자 하는 값이 **부모 노드보다 작다면 왼쪽** 자식 노드를, **부모 노드보다 크다면 오른쪽** 자식 노드를 확인하는 작업을 찾고자 하는 값을 발견할 때까지 반복한다.

`4단계` 원하던 원소를 찾았다면 탐색을 종료한다.

### 트리의 순회 ###
- 트리 자료구조에 포함된 노드를 특정한 방법으로 한 번씩 방문하는 방법을 의미한다!
- 대표적인 트리 순회 방법
    - `전위순회 (pre-order traverse)` : **루트를 먼저 방문**하는 방식
    - `중위순회 (in-order traverse)` : **왼쪽 자식을 먼저 방문**한 다음에 루트를 방문하는 방식
    - `후위순회 (post-order traverse)` : **오른쪽 자식을 방문**한 뒤에 루트를 방문하는 방식

### 트리 순회 예시 ###
- **전위 순회** : A → B → D → E → C → F → G
- **중위 순회** : D → B → E → A → F → C → G
- **후위 순회** : D → E → B → F → G → C → A

### 트리 순회 구현 코드 ###

```python
class Node:
    def __init__(self, data, left_node, right_node):
        self.data = data
        self.left_node = left_node
        self.right_node = right_node

# 전위 순회
def pre_order(node):
    print(node.data, end = " ")
    if node.left_node != None:
        pre_order(tree[node.left_node])
    if node.right_node != None:
        pre_order(tree[node.right_node])

# 중위 순회
def in_order(node):
    if node.left_node != None:
        in_order(tree[node.left_node])
    print(node.data, end = " ")
    if node.right_node != None:
        in_order(tree[node.right_node])

# 후위 순회
def post_order(node):
    if node.left_node != None:
        post_order(tree[node.left_node])
    if node.right_node != None:
        post_order(tree[node.right_node])
    print(node.data, end = " ")

n = int(input())
tree = {}

for i in range(n):
    data, left_node, right_node = input().split()
    if left_node == "None":
        left_node = None
    if right_node == "None":
        right_node = None
    tree[data] = Node(data, left_node, right_node)

pre_order(tree["A"])
print()
in_order(tree["A"])
print()
post_order(tree["A"])
```