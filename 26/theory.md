## Решения различных типов задания 26

#### Тип 1. Системный администратор
```python
f = open('26_27423.txt')

sn = f.readline().split()
s = int(sn[0])
n = int(sn[1])

data = [int(i.replace('\n','')) for i in f.readlines()]
data.sort()

# первая часть
smax = []
for i in data:
	if sum(smax) + i > s:
		break
	smax.append(i)

a1 = data.index(i)	# первый ответ

# вторая часть

l = []
for j in data:
	if j - i <= s - sum(smax):
		l.append(j)

a2 = max(l)			# второй ответ


print(a1, a2)
```

*Смотрите больше вариантов решения [здесь](/26/sdamgia/Системный%20администратор%20и%20архив/27423.md)*
