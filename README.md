# Лабораторная работа 0

## ЗАДАНИЕ
<b> Задача </b>: реализовать алгоритм перемножения матриц <br>
<b> Язык </b>: C++ или Python <br>
<b> Входные данные </b>: 2 матрицы размером от 100х100 до 2000х2000. <br>
<b> Выходные данные </b>: проверка корректности перемножения + время вычисления <br>
<b> Реализация должна содержать 2 функции перемножения матриц </b>: на CPU и на GPU с применением CUDA. <br>
Отчет о проделанной лабораторной работе - это git-репозиторий с исходным кодом реализации + описание проделанной работы там же в readme. <br>
Необходимо описать реализацию, объяснив, что конкретно было распараллелено и почему.  <br>
<b>Провести эксперименты </b>: перемножить матрицы разных размеров, посчитать ускорение. Результаты привести в виде таблицы. <br>

## СРЕДА
<b>Язык программирования</b>: Python, v = 3.x.x <br>
<b>IDE</b>: google colab <br>
<b>GPU</b>: NVIDIA Tesla K80 <br>

## ОПИСАНИЕ
При выполнении первой лабораторной работы проводились исследования на тему сравнения CPU И GPU. Был написан параллельный алгоритм перемножения матриц. Программа перемножает квадратные матрицы размером Size x Size. Алгоритм с разделяемой памятью реализует блочный алгоритм перемножения матриц.. Второй алгоритм создаёт многократное копирование данных для нити и перемножает матрицы стандартным способом. GPU-функция перемножения матриц представляет собой ядро на C, которое преобразуется в Python-код. Также результаты для CPU, GPU выведены через print .

<br><br>
Для эксперимента были использованы матрицы, размерности которых кратны 32, чтобы загрузка блоков GPU была максимальной.

## РЕЗУЛЬТАТЫ ВЫЧИСЛЕНИЙ

|     | Время на CPU | Время на GPU |    Дельта  |
|----:|-------------:|-------------:|-----------:|
| 128 |     3.0748   |     0.9866   |   2.0882   |
| 256 |    24.2892   |     0.0068   |  24.2823   |
| 512 |   192.6665   |     0.0233   | 192.6431   |

