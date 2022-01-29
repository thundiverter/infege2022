```python
f = open('b.txt')
n = int(f.readline())
ans = 0
d = 2 ** 40
for lines in range(n):
    x, y, z = sorted(map(int, f.readline().split()))
    ans += z
    r1 = abs(z - x)
    r2 = abs(z - y)
    tmp = [r1, r2]
    for i in tmp:
        if (i % 109 != 0) and (i < d) and (i != 0):
            d = i
if ans % 109 != 0:
    print(ans)
else:
    print(ans - d)

```
