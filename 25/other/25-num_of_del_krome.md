```python
for i in range(174457, 174506):
    tmp = []
    for y in range(2, i):
        if i % y == 0:
            tmp.append(y)
        if len(tmp) > 2:
            tmp.clear()
            break
    if tmp: print(tmp)
```
