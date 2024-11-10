## Задача 1
> _С помощью команд эмулятора git получить следующее состояние проекта (сливаем master с first, перебазируем second на master)_

<img width="685" alt="image" src="https://github.com/user-attachments/assets/af08b3d8-8e4f-4ca6-a51d-6eba273c595e">


## Задача 2
> _Создать локальный git-репозиторий. Задать свои имя и почту (далее – coder1). Разместить файл prog.py с какими-нибудь данными. Прислать в текстовом виде диалог с git._

```
e:\git\config\pr4>git init
Initialized empty Git repository in E:/git/config/pr4/.git/

e:\git\config\pr4>git config --global user.name "coder1"

e:\git\config\pr4>git config --global user.email "coder1@email.com"

e:\git\config\pr4>echo "#print('Hello, world!')" > prog.py

e:\git\config\pr4>git add prog.py

e:\git\config\pr4>git commit -m "add prog.py"
[master (root-commit) b625377] add prog.py
 1 file changed, 1 insertion(+)
 create mode 100644 prog.py
```

## Задача 3
> _Прислать список набранных команд и содержимое git log._



## Задача 4
> _Написать программу на Питоне (или другом ЯП), которая выводит список содержимого всех объектов репозитория. Воспользоваться командой "git cat-file -p"_

