## Задача 1
> _Реализовать на Jsonnet приведенный пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY._

```jsonnet

```

## Задача 2
> _Реализовать на Dhall приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY._

```

```

### Реализовать грамматики, описывающие следующие языки (для каждого решения привести БНФ). Код решения должен содержаться в переменной BNF:
## Задача 3
> _Язык нулей и единиц._

```py
BNF = '''
E = l | l E
l = 0 | 1 
'''
```
<img width="300" alt="image" src="https://github.com/user-attachments/assets/82964706-d28f-441f-b47a-529b6db19e04">

## Задача 4
> _Язык правильно расставленных скобок двух видов._

```py
BNF = '''
E = l 
l = () | {} | ( l ) | { l }
'''
```
<img width="300" alt="image" src="https://github.com/user-attachments/assets/87ea90e9-e814-404f-8b25-69620a74b21a">


## Задача 5
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
<img width="260" alt="image" src="https://github.com/user-attachments/assets/ccbeb2bf-e41c-40bd-a49d-423fe4f50522">

