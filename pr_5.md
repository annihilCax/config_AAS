## Задача 1
> _Изучите возможности просмотра байткода ВМ CPython._
> _Опишите по шагам, что делает каждая из следующих команд (приведите эквивалентное выражение на Python)_
> 11 0 LOAD_FAST 0 (x) 2 LOAD_CONST 1 (10) 4 BINARY_MULTIPLY 6 LOAD_CONST 2 (42) 8 BINARY_ADD 10 RETURN_VALUE



## Задача 2
> Что делает следующий байткод (опишите шаги его работы)? Это известная функция, назовите ее.

```
  5           0 LOAD_CONST               1 (1)
              2 STORE_FAST               1 (r)

  6     >>    4 LOAD_FAST                0 (n)
              6 LOAD_CONST               1 (1)
              8 COMPARE_OP               4 (>)
             10 POP_JUMP_IF_FALSE       30

  7          12 LOAD_FAST                1 (r)
             14 LOAD_FAST                0 (n)
             16 INPLACE_MULTIPLY
             18 STORE_FAST               1 (r)

  8          20 LOAD_FAST                0 (n)
             22 LOAD_CONST               1 (1)
             24 INPLACE_SUBTRACT
             26 STORE_FAST               0 (n)
             28 JUMP_ABSOLUTE            4

  9     >>   30 LOAD_FAST                1 (r)
             32 RETURN_VALUE
```

## Задача 3
> Приведите результаты из задач 1 и 2 для виртуальной машины JVM (Java) или .Net (C#).

```

```

### log
```

```


## Задача 4
> Работа с qemu. Скачать и установить ISO-образ Alpine Linux для виртуальных машин с официального сайта. Создать с помощью qemu образ жесткого диска (опция -f qcow2). Объем диска 500 Мб. Запустить Alpine Linux с CD-ROM. Установить систему на sda. Изменить motd. Загрузиться уже с sda. Прислать полный список команд для установки и загрузки, а также скриншот с motd, где фигурируют ваши имя и фамилия.
