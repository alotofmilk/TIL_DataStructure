# π¦**Stack**

> **λ¨Όμ  λ€μ΄μ¨** λ°μ΄ν°κ° **λμ€μ λκ°λ** ννμ μλ£κ΅¬μ‘°

**μ μνμΆ** λ°©μμΌλ‘ μλνλ€. μ¦, μκ΅¬μ μΆκ΅¬κ° λμΌν νν. **λ°μ€λ₯Ό μ°¨κ³‘μ°¨κ³‘ μμ μ¬λ¦¬λ λͺ¨μ΅**μ μκ°ν΄λ³΄λ©΄ λμμ΄ λ  κ²μ΄λ€!

```python
stack = []

# μ½μ(5) - μ½μ(2) - μ½μ(3) - μ½μ(7) - μ­μ () - μ½μ(1) - μ½μ(4) - μ­μ ()
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

# μ΅μλ¨ μμλΆν° μΆλ ₯νκΈ°
print(stack[::-1])
# μ΅νλ¨ μμλΆν° μΆλ ₯νκΈ°
print(stack)

# μ€ν κ²°κ³Ό 1 3 2 5
# μ€ν κ²°κ³Ό 5 2 3 1
```

# π **Queue**

> **λ¨Όμ  λ€μ΄μ¨** λ°μ΄ν°κ° **λ¨Όμ  λκ°λ** ννμ μλ£κ΅¬μ‘°

**μ μμ μΆ** λ°©μμΌλ‘ μλνλ€. μκ΅¬μ μΆκ΅¬κ° λͺ¨λ λ«λ €μλ **ν°λ**μ μκ°ν΄λ³΄λ©΄ μ΄ν΄νκΈ° μ¬μμ§λ€.

```python
from collections import deque

# ν(Queue) κ΅¬νμ μν΄ deque λΌμ΄λΈλ¬λ¦¬λ₯Ό μ¬μ©
queue = deque()

# μ½μ(5) - μ½μ(2) - μ½μ(3) - μ½μ(7) - μ­μ () - μ½μ(1) - μ½μ(4) - μ­μ ()
queue.append(5)
queue.append(2)
queue.append(3)
queue.append(7)
queue.popleft()
queue.append(1)
queue.append(4)
queue.popleft()

# λ¨Όμ  λ€μ΄μ¨ μμλλ‘ μΆλ ₯
print(queue)
# μ­μμΌλ‘ λ°κΏ μΆλ ₯
queue.reverse()
print(queue)

# μ€ν κ²°κ³Ό deque([3,7,1,4])
# μ€ν κ²°κ³Ό deque([4,1,7,3])
```