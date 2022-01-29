### Решения различных типов задания 24

#### Тип 1
> Опре­де­ли­те мак­си­маль­ное ко­ли­че­ство иду­щих под­ряд сим­во­лов, среди ко­то­рых каж­дые два со­сед­них раз­лич­ны.

*Вариант решения 1:*
```python
with open('24.txt', 'r') as f:
	s = list(f.readline())
	maxlen = 0 # максимальная длина
	l = 1 # текущая длина
	
	for i in range(1, len(s)):
		if s[i] != s[i - 1]:
			l += 1
			if l > maxlen:
				maxlen = l
		else:
			l = 1

print(maxlen)
```
*Вариант решения 2:*
```python
import re
f = open('24.txt')
s = f.readline()[:-2]

m = re.split(r'(\w)\1', s)
p = [len(j) + 1 for j in m]

print(max(p))
```

#### Тип 2
> Опре­де­ли­те длину самой длин­ной по­сле­до­ва­тель­но­сти, со­сто­я­щей из сим­во­лов X. Хотя бы один сим­вол X на­хо­дит­ся в по­сле­до­ва­тель­но­сти.

```python
f = open('24.txt')

s = f.readline()[:-2]
s = s.replace('Y', ' ').replace('Z', ' ')
s = s.split()

p = [len(i) for i in s]

print(max(p))
```

#### Тип 3
> Опре­де­ли­те мак­си­маль­ную длину це­поч­ки вида XYZXYZXYZ... (со­став­лен­ной из фраг­мен­тов XYZ, по­след­ний фраг­мент может быть не­пол­ным).

```python
import re
f = open('24.txt')
s = f.readline()[:-2]

m = re.findall(r'(?:XYZ)+(?:XY?)?', s)
p = [len(j) for j in m]

print(max(p))
```

#### Тип 5
> Тек­сто­вый файл со­дер­жит толь­ко за­глав­ные буквы ла­тин­ско­го ал­фа­ви­та (ABC…Z). Опре­де­ли­те сим­вол, ко­то­рый чаще всего встре­ча­ет­ся в файле сразу после буквы A.

```python
import re
f = open('24.txt')

a = f.readline()

l = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
c = {}
for i in l:
	c[i] = 0

m = re.findall(r'A\w?', a)

for i in m:
	c[i[1]] += 1

print( max(c, key=c.get) ) 
```
