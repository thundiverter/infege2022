## Задание 15 - числовые отрезки

```python
p1, p2, q1, q2 = 2, 10, 6, 14
P = [i / 10 for i in range(p1 * 10, p2 * 10 + 1)]
Q = [i / 10 for i in range(q1 * 10, q2 * 10 + 1)]

minA = min(p1, q1) * 10 - 1
maxA = max(p2, q2) * 10 + 1

def f(x, A):
    return ((x in A) <= (x in P)) or (x in Q)

A = set([i / 10 for i in range(10, 201)])

for x in [i / 10 for i in range(10, 201)]:
    if not f(x, A):
        A.remove(x)

print(sorted(A))
print('Answer:', len(A) - 1)
```

**Наименьшая длина:**
```python
A = set()

for x in [i / 10 for i in range(minA, maxA)]:
    if not f(x, A):
        A.add(x)
```

**Наибольшая длина:**
```python
A = set([i / 10 for i in range(minA, maxA)])

for x in [i / 10 for i in range(minA, maxA)]:
    if not f(x, A):
        A.remove(x)
```

**Длина промежутка:**
```python
print(len(A) - 1)
```

**Количество элементов во множестве:**
```python
print(len(A))
```
