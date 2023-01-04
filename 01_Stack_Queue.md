# 📦**Stack**

> **먼저 들어온** 데이터가 **나중에 나가는** 형태의 자료구조

**선입후출** 방식으로 작동한다. 즉, 입구와 출구가 동일한 형태. **박스를 차곡차곡 쌓아 올리는 모습**을 생각해보면 도움이 될 것이다!

```python
stack = []

# 삽입(5) - 삽입(2) - 삽입(3) - 삽입(7) - 삭제() - 삽입(1) - 삽입(4) - 삭제()
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

# 최상단 원소부터 출력하기
print(stack[::-1])
# 최하단 원소부터 출력하기
print(stack)

# 실행 결과 1 3 2 5
# 실행 결과 5 2 3 1
```

# 🚄 **Queue**

> **먼저 들어온** 데이터가 **먼저 나가는** 형태의 자료구조

**선입선출** 방식으로 작동한다. 입구와 출구가 모두 뚫려있는 **터널**을 생각해보면 이해하기 쉬워진다.

```python
from collections import deque

# 큐(Queue) 구현을 위해 deque 라이브러리를 사용
queue = deque()

# 삽입(5) - 삽입(2) - 삽입(3) - 삽입(7) - 삭제() - 삽입(1) - 삽입(4) - 삭제()
queue.append(5)
queue.append(2)
queue.append(3)
queue.append(7)
queue.popleft()
queue.append(1)
queue.append(4)
queue.popleft()

# 먼저 들어온 순서대로 출력
print(queue)
# 역순으로 바꿔 출력
queue.reverse()
print(queue)

# 실행 결과 deque([3,7,1,4])
# 실행 결과 deque([4,1,7,3])
```