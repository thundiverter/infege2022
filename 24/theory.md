### Решения различных типов задания 24

#### Тип 1
> Опре­де­ли­те мак­си­маль­ное ко­ли­че­ство иду­щих под­ряд сим­во­лов, среди ко­то­рых каж­дые два со­сед­них раз­лич­ны.

```python
with open('24.txt', 'r') as f:
	s = list(f.readline())
	maxlen = 0
	l = 1
	
	for i in range(1, len(s)):
		if s[i] != s[i - 1]:
			l += 1
			if l > maxlen:
				maxlen = l
		else:
			l = 1

print(maxlen)
```

#### Тип 2
> Опре­де­ли­те длину самой длин­ной по­сле­до­ва­тель­но­сти, со­сто­я­щей из сим­во­лов X. Хотя бы один сим­вол X на­хо­дит­ся в по­сле­до­ва­тель­но­сти.

```python
with open('24.txt', 'r') as f:
	s = list(f.readline())
	maxlen = 0
	l = 1
	
	for i in range(1, len(s)):
		if s[i] == s[i - 1] == 'X':
			l += 1
			if l > maxlen:
				maxlen = l
		else:
			l = 1

print(maxlen)
```
