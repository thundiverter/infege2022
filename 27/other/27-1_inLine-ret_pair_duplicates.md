```python
from numpy import array as ar

f = open('b.txt')
a = ar(tuple(map(int, f.readlines()))[1:])
pmax = {0, 0}
for m in enumerate(a):
    for n in enumerate(a):
        if m[0] != n[0]:
            if (abs(m[1] - n[1]) % 2 == 0) and ((m[1] % 17 == 0) or (n[1] % 17 == 0)):
                if (m[1] + n[1]) > sum(pmax):
                    pmax = {m[1], n[1]}
print(pmax)
```
