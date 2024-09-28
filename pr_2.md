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
```
pipdeptree --graph-output dot > matplotlib_deps.dot
```
```
dot -Tpng matplotlib_deps.dot -o matplotlib_deps.png
```
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
>_Решить на MiniZinc задачу о зависимостях пакетов для рисунка, приведенного ниже._
![image](https://github.com/user-attachments/assets/0aaad5ff-aa8c-4310-b217-f78bc92ea6e6)

```
int: menu = 6; 
int: dropdown = 5;  
int: icons = 2; 

array[1..6] of tuple(int, int, int): menu_versions = [(1,0,0), (1,1,0), (1,2,0), (1,3,0), (1,4,0), (1,5,0)];
array[1..5] of tuple(int, int, int): dropdown_versions = [(1,8,0), (2,0,0), (2,1,0), (2,2,0), (2,3,0)];
array[1..2] of tuple(int, int, int): icons_versions = [(1,0,0), (2,0,0)];
  
var 1..menu: menu_version;
var 1..dropdown: dropdown_version;
var 1..icons: icons_version;

constraint menu_version >= 2 -> dropdown_version >= 2;  
constraint menu_version == 1 -> dropdown_version == 1;  
constraint dropdown_version >= 2 -> icons_version == 2;  

solve satisfy;

output [
  "menu: v", show(menu_versions[menu_version]), "\n",
  "dropdown: v", show(dropdown_versions[dropdown_version]), "\n",
  "icons: v", show(icons_versions[icons_version]), "\n"
];
```
<img width="595" alt="image" src="https://github.com/user-attachments/assets/14f546c0-be86-48f1-9cdc-927edfa13e25">


## Задача 6
>_Решить на MiniZinc задачу о зависимостях пакетов для следующих данных:_
```
root 1.0.0 зависит от foo ^1.0.0 и target ^2.0.0.
foo 1.1.0 зависит от left ^1.0.0 и right ^1.0.0.
foo 1.0.0 не имеет зависимостей.
left 1.0.0 зависит от shared >=1.0.0.
right 1.0.0 зависит от shared <2.0.0.
shared 2.0.0 не имеет зависимостей.
shared 1.0.0 зависит от target ^1.0.0.
target 2.0.0 и 1.0.0 не имеют зависимостей.
```
<img width="559" alt="image" src="https://github.com/user-attachments/assets/b1755426-7304-4181-a0e8-8aac9a3793d5">

```
int: foo = 2;
int: left = 1;
int: right = 1;
int: shared = 2;
int: target = 2;
int: root = 1;

array[1..foo] of tuple(int, int, int): foo_versions = [(1,0,0), (1,1,0)];
array[1..left] of tuple(int, int, int): left_versions = [(1,0,0)];
array[1..right] of tuple(int, int, int): right_versions = [(1,0,0)];
array[1..shared] of tuple(int, int, int): shared_versions = [(1,0,0), (2,0,0)];
array[1..target] of tuple(int, int, int): target_versions = [(1,0,0), (2,0,0)];

tuple(int, int, int): root_versions = (1,0,0);


var 1..foo: foo_version;
var 1..left: left_version;
var 1..right: right_version;
var 1..shared: shared_version;
var 1..target: target_version;
var 1..root: root_version;

constraint root_version == 1 -> foo_version >= 1 /\ target_version >= 2;
constraint foo_version == 2 -> left_version >= 1 /\ right_version >= 1;
constraint left_version == 1 -> shared_version >= 1;
constraint right_version == 1 -> shared_version < 2;
constraint shared_version == 1 -> target_version >= 1 /\ target_version <= 2;

solve satisfy;

output [
"root: v", show(root_versions), "\n",
"foo: v", show(foo_versions[foo_version]), "\n",
"left: v", show(left_versions[left_version]), "\n",
"right: v", show(right_versions[right_version]), "\n",
"shared: v", show(shared_versions[shared_version]), "\n",
"target: v", show(target_versions[target_version]), "\n"
];
```

## Задача 7
>_Представить задачу о зависимостях пакетов в общей форме. Здесь необходимо действовать аналогично реальному менеджеру пакетов. То есть получить описание пакета, а также его зависимости в виде структуры данных. Например, в виде словаря. В предыдущих задачах зависимости были явно заданы в системе ограничений. Теперь же систему ограничений надо построить автоматически, по метаданным._
```
```
