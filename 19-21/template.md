## Шаблоны решений заданий 19-21

### Одна куча
#### 19
```python
# A, B, Smax = ...

def f(s, t):
    if s >= Smax or t > 3:
        return t == 3
    return f(s+1, t+1) or f(s+4, t+1) or f(s*5, t+1)

for i in range(A, B + 1):
    if f(i, 1):
        print(i)
        break
```

#### 20
```python
# A, B, Smax = ...

def f(s, t):
    if s >= Smax or t > 4:
        return t == 4
    if t % 2 != 0:
        return f(s+1, t+1) or f(s+4, t+1) or f(s*5, t+1)
    return f(s+1, t+1) and f(s+4, t+1) and f(s*5, t+1)

for i in range(A, B + 1):
    if f(i, 1):
        print(i)
```

#### 21
```python
# A, B, Smax = ...

def f(s, t):
    if s >= Smax or t > 5:
        return t == 3 or t == 5
    if t % 2 == 0:
        return f(s+1, t+1) or f(s+4, t+1) or f(s*5, t+1)
    return f(s+1, t+1) and f(s+4, t+1) and f(s*5, t+1)

for i in range(A, B + 1):
    if f(i, 1):
        print(i)
        break
```
