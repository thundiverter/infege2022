# Контрольная работа №6
<!--*Вариант 22*-->

### Задание 1
> 338 байт заняли сведения о 26 записях. Каждая запись (целое число байт) состоит из служебной информации и 7 заглавных букв русского алфавита, закодированных равномерно минимальным количеством бит. Чему равен размер служебной информации в каждой записи в байтах?

```
I26 = 338 байт
N = 7

I = I26 / 26 = 13 байт = 104 бит

N = 2^i
4 < 7 < 8
2^2 < 2^i < 2^3
2 < i < 3
i = 2 бит

i7 = 2 * 7 = 14 бит

104 - 14 = 90 бит = 11,25 байт ~ 12 байт
```
**Ответ:** 12.

### Задание 2
> Для хранения изображения (растровое, без сжатия) 112х136 отведено 5966 байт. Какое максимальное количество цветов в изображении?

```
Дано:
KN = 112 * 136
I = 5966 байт

Найти:
M - ?

Решение:
M = 2^i
I = KN * i

i = I / KN = (5966 * 8) / (112 * 136) = 3,13... ~ 3 бит

M = 2^3 = 8
```
**Ответ:** 8.


### Задание 3
```
239 * 8 - (256 - 239) = 1895
```
**Ответ:** 1895.

### Задание 4
```python
def f(s, t):
    if s>=88 or t > 4:
        return t == 4
    if t % 2 != 0:
        return f(s+1, t+1) or f(s*2, t+1)
    return f(s+1, t+1) and f(s*2, t+1)

for i in range(1, 88+1):
    if f(i, 1):
        print(i)
```
**Ответ:** 42.

### Задание 5
```python
def f(s, t):
    if s>=88 or t > 5:
        return t == 3 or t == 5
    if t % 2 == 0:
        return f(s+1, t+1) or f(s*2, t+1)
    return f(s+1, t+1) and f(s*2, t+1)

for i in range(1, 88+1):
    if f(i, 1):
        print(i)
        break
```
**Ответ:** 41.

### Задание 6
```python
def f(n):
    if n < 5: return 1
    return n + f(n-3) - f(n//2)

maxs = 0

for i in range(38, 88 + 1):
    maxs = max(maxs, sum([int(j) for j in str(i)]) )

print(maxs)
```
**Ответ:** 16.

### Задание 7
```python
for a in range(-100, 100):
    flag = True

    for x in range(100):
        for y in range(100):
            if (3*x + 7*y >= 50) or (x + y <= a):
                pass
            else:
                flag = False
                break
    
    if flag:
        print(a)
        break
```
**Ответ:** 16.

### Задание 8
![](https://github.com/Thundiverter/infege2022/blob/main/repofiles/298294749724314.png?raw=true)


**Ответ:** 59.

### Задание 9
```python
s = ''
l = '0123456789AB'

for i in range(5, 11+1):
    n = 1277
    a = ''

    while n > 0:
        a = l[n % i] + a
        n //= i
    
    s += a

s = s.replace('1', '')

print(s)
b = {}
for i in l:
    b[i] = s.count(i)
print(b)
```
**Ответ:** 2 | 5.

### Задание 10
```python
from itertools import *

a = product('АБВ', repeat=6)

index = 0
for i in a:
    w = ''.join(i)
    if w.count('БА') != 0: continue

    index += 1

    if index == 113: print(w)
```
**Ответ:** АВББВА.

### Задание 11
```python
a = 36**86 - 36**65 + 6**50 - 6**24 - 36

p = {}
for i in range(5): p[i] = 0

while a > 0:
    p[a % 5] += 1
    a //= 5

print(p)
```
**Ответ:** 0 | 2.

### Задание 12
> В электронной таблице 18 на 18 клеток лежат камушки по формуле 4 + ((1 + номер клетки + 2 * номер столбца) остаток от деления на 12). Петя идёт п клеткам из 1-1 и может только вправо или вниз. Максимально соберёт камушек?

> [Скачать файл с решением](https://github.com/Thundiverter/infege2022/raw/main/repofiles/49629423947.xlsx)

**Ответ:** 413.

### Задание 13
> После записи в режиме 22050 Гц 16-битного моно звука получили файл размером 61 мегабайт. Сколько примерно минут шла запись?

```
I = 61 Мбайт
p = 22050 * 16 * 1

t = I / p * (1/60) = (61 * 1024 * 1024 * 8) / (22050 * 16) * (1/60) = 24.17352079 ~ 24 мин
```
**Ответ:** 24.

### Задание 14
```python
from itertools import *
a = product('ПЕТЯ', repeat=6)

count = 0
for i in a:
    if i.count('Е') >= 3: count += 1

print(count)
```
**Ответ:** 694.

### Задание 15
```python
for i in range(171, 1000):
    s = 'З' * i

    while ('ЗЗЗ' in s) or ('ЪЪЪ' in s):
        if 'ЗЗЗ' in s: s = s.replace('ЗЗЗ', 'Ъ', 1)
        else: s = s.replace('ЪЪЪ', 'З', 1)
    
    if s == 'ЗЗЪ':
        print(i)
        break
```
**Ответ:** 189.

### Задание 16
```python
for i in range(10_000, 100_000):
    K, O, T = i, 0, 0

    while K > 0:
        O, T, K = O + 1 if K % 10 < 4 else O, T + 1 if K % 10 > 6 else T, K // 10
    
    if O == 3 and T == 1:
        print(i)
        break
```
**Ответ:** 10047.

### Задание 17

Исходная таблица:
```
_ _ _ _
_ 1 0 _
1 1 _ 0
1 _ 1 0
```

```python
print('x y z w')
r = range(2)

for x in r:
    for y in r:
        for z in r:
            for w in r:
                if (y == z) or w or (not(x) and not(y)):
                    pass
                else:
                    print(x, y, z, w)
```

Получим:
```
x y z w
0 1 0 0
1 0 1 0
1 1 0 0
```

Основываясь на полученных данных, восстановим изначальную таблицу:
```
x y z w
0 1 0 0
1 1 0 0
1 0 1 0
```
**Ответ:** xyzw.

### Задание 18
```python
def f(x, y):
    if x > y: return 0
    if x == y: return 1
    if x in [26, 27]: return 0
    return f(x+1, y) + f(x*3, y) + f(x+12, y)

print( f(2, 19) * f(19, 20) * f(20, 45) )
```
**Ответ:** 135.


### Задание 19
```python
count = 0

for i in range(2287, 11_800 + 1):
    s = sum([int(j) for j in str(i)]) ** 2

    if i % s == 0:
        count += 1

print(count)
```
**Ответ:** 81.


### Задание 20
```python
nums = []

count = 0
for n in range(4_003_173, 4_202_256+1)[::-1]:
    if count > 2: break
    if str(n)[-2:] != '31': continue

    flag = True
    for j in range(2, int(n**0.5)+1):
        if n % j == 0:
            flag = False
            break
    
    if flag:
        nums.append(n)
        count += 1

print( abs(nums[0] - nums[1]) )
```
**Ответ:** 800.

### Задание 21
![](https://github.com/Thundiverter/infege2022/blob/main/repofiles/9756290287892790.png?raw=true)

![](https://github.com/Thundiverter/infege2022/blob/main/repofiles/298294749724314_2083.png?raw=true)
**Ответ:** 11.

### Задание 22
> Чему равен модуль разности количества А и С в файле *inf.txt*?
> ```python
> s = ''
> v = 0
> for i in range(1774):
>   v = (v + i + 66 + i * 38 + (i * 25) % 777) % 5
>   s += 'ABCBCA'[v]
> open('inf.txt', 'w').write(s)
> ```

```python
f = open('inf.txt')
s = f.readline()
print( abs( s.count('A') - s.count('C') ) )
```
**Ответ:** 438.

### Задание 23
```python
from itertools import *
f = open('inf.txt')
s = f.readline()

m = {}
for i in product('ABC', repeat=3):
    m[''.join(i)] = 0

for i, j, k in zip(s, s[1:], s[2:]):
    m[i+j+k] += 1

print(max(m, key=m.get))
```
**Ответ:** BBC | CBB.

### Задание 24
```python
from itertools import *
f = open('inf.txt')
s = f.readline()
s = s.replace('AB', 'D')

m = {}
for i in product('ABCD', repeat=4):
    m[''.join(i)] = 0

for i, j, k, l in zip(s, s[1:], s[2:], s[3:]):
    m[i+j+k+l] += 1

print(m)
print(max(m, key=m.get))
```
**Ответ:** BCCB.

### Задание 25
```python
f = open('inf.txt')
s = f.readline()
s = s.replace('AB', 'D')

q = []
for i in s:
    if i == 'A': q.append(10)
    if i == 'B': q.append(11)
    if i == 'C': q.append(12)
    if i == 'D': q.append(13)

count = 0
for i, j in zip(q, q[1:]):
    c = 0
    if i % 2 == 0: c += 1
    if j % 2 == 0: c += 1

    if c == 1: count += 1

print(count)
```
**Ответ:** 709.

### Задание 26
```python
f = open('inf.txt')
s = f.readline()
s = s.replace('AB', 'D')

s = s.split('D')

l = [len(i) for i in s]
print(max(l))
```
**Ответ:** 530.

### Задание 27
```python
m = 0

for n in range(13_523, 19_376 + 1):
    s = sum([int(i) for i in str(n)])

    m = max(m, n % s)

print(m)
```
**Ответ:** 34.
