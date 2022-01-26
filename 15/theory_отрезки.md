## Задание 15 - числовые отрезки

```python
def f(x, A):
    return (130 <= x <= 171) <= (((150 <= x <= 185) and (x not in A)) <= (not (130 <= x <= 171)))


A = []
for x in range(1, 10000):
    i = x / 10
    if not f(i, A):
        A.append(i)

print(A)
```

**Наименьшая длина:**
```python
A = []

for x in range(1, 10000):
    i = x / 10
    if not f(i, A):
        A.add(i)
```

**Наибольшая длина:**
```python
A = [i / 10 for i in range(1, 10000)]

for x in range(1, 10000):
    i = x / 10
    if not f(i, A):
        A.remove(i)
```
