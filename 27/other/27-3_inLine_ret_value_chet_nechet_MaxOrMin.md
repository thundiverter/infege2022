```python
f = open('a.txt')
n = int(f.readline())
smx = sav = smn = 0
d = 2 ** 20
for i in range(n):
    x, y, z = sorted(map(int, f.readline().split()))
    smn += x; sav += y; smx += z
    dtmp1 = abs(z - y)  # x -
    dtmp2 = abs(z - x)  # x -
    tmp = [dtmp2, dtmp1]
    for item in tmp:
        if (item % 2 != 0) and (item < d) and (item != 0):
            d = tmp
if (sav + smn) % 2 == 0:  # + smx
    smx -= d  # smn +
print(smx)  # smn

```
