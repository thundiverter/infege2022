```python
answ = []
for num in range(568023, 569230 + 1):
    c = 0
    for d in range(1, num + 1):
        if num % d == 0:
            c += 1
    answ.append((c, num))
answ.sort(key=lambda i: i[0])
[print(i, end='\n') for i in answ]

```
