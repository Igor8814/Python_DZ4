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
Задайте последовательность чисел.
Напишите программу, которая выведет
список неповторяющихся элементов 
исходной последовательности.
~~~
lst = list(map(int, input("Введите числа через пробел:\n").split()))
print(f"Исходный список: {lst}")
new_lst = []
[new_lst.append(i) for i in lst if i not in new_lst]
print(f"Список из неповторяющихся элементов: {new_lst}")
~~~
Задана натуральная степень k.
Сформировать случайным образом
список коэффициентов (значения от 0 до 100)
многочлена и записать в файл многочлен степени k.
Пример:
- k=2 => 2*x² + 4*x + 5 = 0 или x² + 5 = 0 или 10*x² = 0
~~~
from random import randint

# Создание случайного числа и коэффициента многочлена
k = int(input('input k '))
lst = [randint(0, 101) for i in range(k + 1)]

# Создание многочлена в виде строки
lst = lst[::-1]
wr = ''
if len(lst) < 1:
    wr = 'x = 0'
else:
    for i in range(len(lst)):
        if i != len(lst) - 1 and lst[i] != 0 and i != len(lst) - 2:
            wr += f'{lst[i]}x^{len(lst) - i - 1}'
            if lst[i + 1] != 0:
                wr += ' + '
        elif i == len(lst) - 2 and lst[i] != 0:
            wr += f'{lst[i]}x'
            if lst[i + 1] != 0:
                wr += ' + '
        elif i == len(lst) - 1 and lst[i] != 0:
            wr += f'{lst[i]} = 0'
        elif i == len(lst) - 1 and lst[i] == 0:
            wr += ' = 0'
print(wr)

# Запись многочлена в файл
with open('fileDz4.txt', 'w') as data:
    data.write(wr)