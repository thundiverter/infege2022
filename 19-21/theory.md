## Задания 19-21

### Две кучи

#### Задание 19
* **x** — количество камней в первой куче (дано в условии);
* **S** — количество камней во второй куче (надо найти);
* **[A, B]** — значения, которые может принимать *S* (A ≤ S ≤ B);
> *В на­чаль­ный мо­мент в пер­вой куче было ***x*** кам­ней, во вто­рой куче — S кам­ней; **A** ≤ S ≤ **B**.*
* **Smax** — количество камней, при котором игрок выигрывает:
> *Игра за­вер­ша­ет­ся в тот мо­мент, когда сум­мар­ное ко­ли­че­ство кам­ней в кучах ста­но­вит­ся не менее **Smax**.*
* **turn** — счётчик ходов (чётный — Петя, нечётный — Ваня).

Пусть будут следующие действия:
* добавить 4 камня;
* увеличить количество камней в 3 раза;

```python
Smax, x, A, B = ...

def f(x, S, turn):
    global Smax
    if turn == 2:
        return (x + S) >= Smax
    return f(x + 4, S, turn + 1) or f(x, S + 4, turn + 1) or f(x * 3, S, turn + 1) or f(x, S * 3, turn + 1)

for i in range(A, B + 1):
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
