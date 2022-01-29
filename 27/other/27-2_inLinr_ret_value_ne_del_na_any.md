```python
f = open("27b.txt")
N = int(f.readline())
otv, mn = 0, 10001
for i in range(N):
    x, y = map(int, f.readline().split())
    otv += max(x, y)
    t = abs(x - y)
    if (t % 3 != 0) and (t < mn):
        mn = t
if otv % 3 != 0:
    print(otv)
else:
    print(otv - mn)

```
