## Задача 1
> _Реализовать на Jsonnet приведенный пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY._

```jsonnet
local groups = ["ИКБО" + "-" + std.toString(i) + "-20" for i in std.range(1, 24)];

local students = [
    { "age": 19, "group": "ИКБО-4-20", "name": "Иванов И.И." },
    { "age": 18, "group": "ИКБО-5-20", "name": "Петров П.П." },
    { "age": 18, "group": "ИКБО-5-20", "name": "Сидоров С.С." },
    { "age": 20, "group": "ИКБО-10-20", "name": "Cпесивцева А.А." }  
];

{
  "groups": groups,
  "students": students,
  "subject": "Конфигурационное управление"
}
```

## Задача 2
> _Реализовать на Dhall приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY._

```

```

## Задачи 3-5
### Реализовать грамматики, описывающие следующие языки (для каждого решения привести БНФ). Код решения должен содержаться в переменной BNF:
> _Язык нулей и единиц._

```py
BNF = '''
E = l | l E
l = 0 | 1 
'''
```
<img width="300" alt="image" src="https://github.com/user-attachments/assets/82964706-d28f-441f-b47a-529b6db19e04">



> _Язык правильно расставленных скобок двух видов._

```py
BNF = '''
E = l 
l = () | {} | ( l ) | { l }
'''
```
<img width="300" alt="image" src="https://github.com/user-attachments/assets/87ea90e9-e814-404f-8b25-69620a74b21a">



> _Язык выражений алгебры логики._

```py
BNF = '''
E = L | ( L ) bin_op ( E )
var = x | y
unar_op = ~
bin_op = & | +
L = var bin_op var | unar_op var | ( var ) 
'''
```
<img width="300" alt="image" src="https://github.com/user-attachments/assets/ccbeb2bf-e41c-40bd-a49d-423fe4f50522">

