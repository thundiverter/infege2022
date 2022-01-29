```python
from numpy import array as ar

f = open('b.txt')
a = ar(tuple(map(int, f.readlines()))[:-2])
otv = 1  # контрольное значение
for m in enumerate(a):
    for n in enumerate(a):
        if m[0] != n[0]:
            tmp = m[-1]*n[-1]
            if (tmp % 11 == 0) and (tmp > otv):
                otv = tmp
print(otv)

```
