Вычислить число c заданной точностью d
Пример:
- при $d = 0.001, π = 3.141.$    $10^{-1} ≤ d ≤10^{-10}$
~~~
from math import pi

d =  int(input("Введите число для заданной точности числа Пи: "))
print(f'число Пи с заданной точностью {d} равно {round(pi, d)}')
~~~

Задайте натуральное число N.
Напишите программу, которая
составит список 
простых множителей числа N.
~~~
n = int(input())
k = 2
l = list()
while k <= n :
    if n % k == 0:
        l.append(k)
        n = n / k
    else:
        k+= 1
print(l) 
~~~
