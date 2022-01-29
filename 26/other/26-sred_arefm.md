```python
sl, ch = {}, {}
l = k = m = 0
f = open("26.txt")
n = int(f.readline())
for i in range(n):
    b = int(f.readline())
    sl[b] = 1
    if b % 2 == 0:
        ch[b] = 1
f.close()
for i in ch:
    for j in ch:
        if i < j:
            if ((i + j) / 2) in sl:
                k += 1
                if i + j > m:
                    m = i + j
print(k, m // 2)

```
