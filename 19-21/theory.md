## Задания 19-21

Ниже приведен шаблон решений заданий 19-21 с двумя кучами. При решении задани задач с одной кучей просто уберите *x* и *xstart*.

---

* **x** — количество камней в первой куче;
* **xstart** — количество камней в первой куче в начале (дано в условии);
* **S** — количество камней во второй куче (надо найти);
* **[A, B]** — значения, которые может принимать *S* (A ≤ S ≤ B);
> *В на­чаль­ный мо­мент в пер­вой куче было ***xstart*** кам­ней, во вто­рой куче — S кам­ней; **A** ≤ S ≤ **B**.*
* **Smax** — количество камней, при котором игрок выигрывает:
> *Игра за­вер­ша­ет­ся в тот мо­мент, когда сум­мар­ное ко­ли­че­ство кам­ней в кучах ста­но­вит­ся не менее **Smax**.*
* **turn** — счётчик ходов (чётный — Петя, нечётный — Ваня).

Пусть будут следующие действия:
* прибавить один;
* увеличить в 2 раза.


#### Задание 19
```python
Smax, xstart, A, B = ...

def f(x, y, p):
	if x + y >= Smax or p > 3:
		return p == 3
	return f(x + 1, y, p + 1) or f(x, y + 1, p + 1) or f(x * 2, y, p + 1) or f(x, y * 2, p + 1)
	
for s in range (A, B + 1):
	if f(xstart, s, 1):
		print(s)
		break
```

#### Задание 20
```python
Smax, xstart, A, B = ...

def f(x, y, p):
	if x + y >= Smax or p > 4:
		return p == 4
	if p % 2 != 0:
		return f(x + 1, y, p + 1) or f(x, y + 1, p + 1) or f(x * 2, y, p + 1) or f(x, y * 2, p + 1)
	return f(x + 1, y, p + 1) and f(x, y + 1, p + 1) and f(x * 2, y, p + 1) and f(x, y * 2, p + 1)

for s in range (A, B + 1):
	if f(xstart, s, 1):
		print(s)
```

#### Задание 21
```python
Smax, xstart, A, B = ...

def f(x, y, p):
	if x + y >= Smax or p > 5:
		return p == 3 or p == 5
	if p % 2 == 0:
		return f(x + 1, y, p + 1) or f(x, y + 1, p + 1) or f(x * 2, y, p + 1) or f(x, y * 2, p + 1)
	return f(x + 1, y, p + 1) and f(x, y + 1, p + 1) and f(x * 2, y, p + 1) and f(x, y * 2, p + 1)

for s in range(A, B + 1):
	if f(xstart, s, 1):
		print(s)
		break
```




<!--#### Задание 19
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
Smax, x, A, B = ...

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

for i in range(A, B + 1):
    if f(x, i, 0):
        print(i)
```-->
