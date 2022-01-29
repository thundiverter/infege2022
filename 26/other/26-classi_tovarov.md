```python
f = open('26.txt')
spent, count_b, v = 0, 0, 4000000
inp = [(tuple(i.strip().split())) for i in f]
A = sorted([int(item) for sub in [[i[0]] * int(i[1]) for i in inp if i[-1] == 'A'] for item in sub])
B = sorted([int(item) for sub in [[i[0]] * int(i[1]) for i in inp if i[-1] == 'B'] for item in sub])
for i in A:
    if spent + i <= v:
        spent += i
for i in B:
    if spent + i <= v:
        spent += i
        count_b += 1
print('Товаров B: ', count_b)
print('Осталось кэша:', v - spent)

```
