```python
f = open('26.txt')
a = tuple(sorted(map(int, f.readlines())))
v, used, i = 9537, 0, 0
while True:
    used += a[i]
    i += 1
    if (used + a[i + 1]) > v: break
print('Users =', i)
while True:
    used -= a[i]
    i += 1
    used += a[i]
    if used > v:
        print('Max size=', a[i - 1])
        break
```
