```python
f = open("bmin.txt")  # делится на 3 минимально возможная
N = int(f.readline())
otv = 0
d1 = []
d2 = []
for i in range(N):
    x, y = map(int, f.readline().split())
    otv += min(x, y)  # max
    tmp = abs(x - y)
    if tmp % 3 == 1: d1.append(tmp)
    if tmp % 3 == 2: d2.append(tmp)
d1 = sorted(d1)[:2]
d2 = sorted(d2)[:2]
if otv % 3 == 0:
    pass
elif otv % 3 == 1:
    if min(d2) < sum(d1):  # sum min
        otv += min(d2)  # - sum
    else:
        otv += sum(d1)  # - min
else:
    if min(d1) < sum(d2):  # sum min
        otv += min(d1)  # - sum
    else:
        otv += sum(d2)  # - min
print(otv)

```
