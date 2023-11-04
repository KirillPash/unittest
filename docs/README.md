# Тестирование быстрой сортировки на Python с помощью Unit тестов
## Описание функции
```
import unittest

def quicksort(array, left, right):
    i = left
    j = right
    pivot = array[(left + right + 1) // 2]
    while (i <= j):
        while (array[i] < pivot):
            i += 1
        while (array[j] > pivot):
            j -= 1
        if (i <= j):
            temp = array[i]
            array[i] = array[j]
            array[j] = temp
            i += 1
            j -= 1
    if (left < j):
        array = quicksort(array, left, j)
    if (i < right):
        array = quicksort(array, i, right)
    return array

class QSortTestCase(unittest.TestCase):
    def test_qsort(self):
        res = quicksort([6, 4, 2, 5, 3], 0, 4)
        self.assertEqual(res, [2, 3, 4, 5, 6])
```
## Входные и выходные данные
- [6, 4, 2, 5, 3]
    - [2, 3, 4, 5, 6]
## Результаты теста
```
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```
