## Задания 19-21

### Две кучи

#### Задание 19
[Условие](https://inf-ege.sdamgia.ru/problem?id=27416)
```python
# x       кол-во камней в первой куче (дано по условию)
# S       кол-во камней во второй куче (надо найти)
# turn    счётчик ходов (чётное - Петя, нечётное - Ваня)

# Дано:
# x = 7 (камней)
# Smax = 77 (камней)

# 1 <= S <= 69

# Действия:
# 1) + 1;
# 2) x 2;

# Найти: S

Smax = 77
x = 7

def f(x, S, turn):
    global Smax
    
    if turn == 2:
        return x + S >= Smax
    else:
        return f(x + 1, S, turn + 1) or f(x, S + 1, turn + 1) or f(x * 2, S, turn + 1) or f(x, S * 2, turn + 1)

for i in range(1, 69):
    if f(x, i, 0):
        print(i)
        break
```

#### Задание 20
```python
Smax = 77
x = 7

def f(x, S, turn):
    global Smax
    
    if turn == 3:
        return x + S >= Smax
    
    if x + S >= Smax:
        return False
    
    if turn % 2 == 0:
                return f(x + 1, S, turn + 1) or f(x, S + 1, turn + 1) or f(x * 2, S, turn + 1) or f(x, S * 2, turn + 1)
    else:
                return f(x + 1, S, turn + 1) and f(x, S + 1, turn + 1) and f(x * 2, S, turn + 1) and f(x, S * 2, turn + 1)

for i in range(1, 69):
    if f(x, i, 0):
        print(i)
```
