```python
c = 1
for a in range(2422000,2422081):
    if all(a % i for i in range(2, a)):
        print(c, a)
    c += 1

```
