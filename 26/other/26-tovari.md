```python
from math import ceil
f = open('26-2.txt')
inp = tuple(map(int, f.readlines()))[1:]
nsk, sk = [], []
[nsk.append(i) for i in inp if i < 101]
[sk.append(i) for i in inp if i > 100]
sk.sort()
s = int(len(sk) / 2)
[nsk.append(i) for i in sk[s:]]
sk = [i * 0.7 for i in sk[:s]]
mx = int(sk[-1] / 0.7)
print(ceil(sum(sk) + sum(nsk)), mx)

```
