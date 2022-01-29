```python
# https://inf-ege.sdamgia.ru/problem?id=27989 - на сайте в файле повторы
f = open('b.txt')
a = set(tuple(map(int, f.readlines()))[1:])
a2 = set()
for m in a:
    for n in a:
        if (m != n) and (((m * n) % 62) == 0):
            a2.add(tuple([m, n]))
a2 = {tuple(item) for item in map(sorted, a2)}
print(len(a2))

```
