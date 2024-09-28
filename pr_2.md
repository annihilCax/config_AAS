## Задача 1
> _Вывести служебную информацию о пакете matplotlib (Python)._
```
py -m pip show matplotlib
```
<img width="523" alt="Снимок экрана 2024-09-23 163637" src="https://github.com/user-attachments/assets/bee7f0a0-55f6-4af9-9062-c417fa48c6f5">


> _Разобрать основные элементы содержимого файла со служебной информацией из пакета._

Name - название пакета\
Version - версия пакета\
Summary - краткое описание\
Home-page - страница пакета\
Author - автор-ы пакета\
Author-email - почтовый адрес пакета-ов\
License - лицензия распространения пакета\

> _Как получить пакет без менеджера пакетов, прямо из репозитория?_
```
git clone https://github.com/matplotlib/matplotlib.git
```

## Задача 2

> _Вывести служебную информацию о пакете express (JavaScript)._
```
npm show express
```
<img width="773" alt="image" src="https://github.com/user-attachments/assets/d7260bba-e964-41c7-bf7b-c0aa54c78e8c">

> _Разобрать основные элементы содержимого файла со служебной информацией из пакета._

Название@версия | Лицензия | Кол-во зависимостей | Кол-во версий\
Краткое описание\
Страница пакета\
Keywords - ключевые слова, описываюшие пакет\
Dist:
- tarball - ссылка на архив пакета
- shasum - контрольная сумма пакета
- integrity - интегритетная контрольная сумма пакета
- unpackedSize - размер распакованного пакета

Dependencies - зависимости\
Maintainers - авторы и поддерживаюшие пакет\
Dist-tags - теги с текущей и следующей версией\
published <когда> by <кем> <почтовый адрес>

> _Как получить пакет без менеджера пакетов, прямо из репозитория?_
```
git clone https://github.com/expressjs/express.git
```

## Задача 3
> _Сформировать graphviz-код и получить изображения зависимостей matplotlib и express._

## Задача 4

>_Решить на MiniZinc задачу о счастливых билетах. Добавить ограничение на то, что все цифры билета должны быть различными (подсказка: используйте all_different). Найти минимальное решение для суммы 3 цифр._
```
include "alldifferent.mzn";

array[1..6] of var 0..9: arr;
constraint all_different(arr);

constraint sum(arr[1..3]) = sum(arr[4..6]);
var int: S = sum(arr[1..3]);

solve minimize S;
output ["Набор чисел: ", show(arr), 
"\nСумма: ", show(S)];
```
<img width="450" alt="image" src="https://github.com/user-attachments/assets/5ba35ffb-ba07-4d82-b15b-28d490cb6a67">

## Задача 5

## Задача 6

## Задача 7
