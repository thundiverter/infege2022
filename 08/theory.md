### Решения различных типов задания 8

Все 5-бук­вен­ные слова, со­став­лен­ные из букв А, О, У, за­пи­са­ны в ал­фа­вит­ном по­ряд­ке. Вот на­ча­ло спис­ка:

1. ААААА
2. ААААО
3. ААААУ
4. АААОА

……


#### Тип 1.1
> За­пи­ши­те слово, ко­то­рое стоит на 210-м месте от на­ча­ла спис­ка (под номером 210).

```python
l = ['А', 'О', 'У']
r = range(len(l))	# 3

count = 0
for a in r:
	for b in r:
		for c in r:
			for d in r:
				for e in r:
					count += 1
					
					if count == 210:
						print(l[a], l[b], l[c], l[d], l[e])
```

#### Тип 1.2
> Ука­жи­те номер пер­во­го слова, ко­то­рое на­чи­на­ет­ся с буквы У.

```python
l = ['А', 'О', 'У']
r = range(len(l))	# 3

count = 0
ans = []
for a in r:
	for b in r:
		for c in r:
			for d in r:
				for e in r:
					count += 1
					
					if a == 2:	# У - третья буква, значит её индекс 2
						ans.append(count)

print(min(ans))
						
```

#### Тип 1.3
> Ука­жи­те номер слова УАУАУ.

```python
l = ['А', 'О', 'У']
r = range(len(l))	# 3

count = 0
for a in r:
	for b in r:
		for c in r:
			for d in r:
				for e in r:
					count += 1
					
					if [a, b, c, d, e] == [2, 0, 2, 0, 2]:
						print(count)
```

#### Тип 1.4
> Под каким но­ме­ром в спис­ке идёт пер­вое слово, в ко­то­ром ***нет*** буквы А?

```python
l = ['А', 'О', 'У']
r = range(len(l))	# 3

count = 0
ans = []
for a in r:
	for b in r:
		for c in r:
			for d in r:
				for e in r:
					count += 1
					
					if 0 not in [a, b, c, d, e]:
						ans.append(count)

print(min(ans))
```
