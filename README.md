# Решение дифференциальных уравнений методом Рунге-Кутты 4-го порядка

## Описание
Это реализация метода Рунге-Кутты четвертого порядка для решения ДУ. Само ДУ задается внутри исходного кода. Результатом работы программы является вывод точек функции.

## Детали
Метод реализован с адаптивным шагом. На каждом этапе происходит 2 вычисления:
1. Вычисление `Y` методом Р-К с шагом `h`.
2. Вычисление `Y*` дважды методом Р-К с шагом `h/2`.
3. После этого `Y` и `Y*` сравниваются. Если разница приемлема (`|Y-Y*|<e`), то шаг `h` увеличивается в два раза. Если `|Y-Y*|>e`, то шаг `h` уменьшается в два раза.

## Компиляция, запуск, вывод
```
$ g++ rk.cpp
$ ./a.out
```
При запуске программы с `h=0.01` и `h=0.001` при `X=0.64` значения `Y` совпадают, что является ожидаемым поведением.