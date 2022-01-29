```python
f = open('bmax.txt')
otv = 0  # 2 ** 40
a = (sorted(tuple(map(int, f.readlines()))[1:])[::-1])[:10]
# sorted(tuple(map(int, f.readlines()))[1:])[:10]
for x in a:
    for y in a:
        for z in a:
            if (x != y) and (y != z) and (z != x):
                if (z + x + y) % 3 == 0 and (z + x + y) > otv:  # <
                    otv = (z + x + y)
print(otv)

```
