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

```
e:\git\config\pr4>cd ..

e:\git\config>git init --bare server
Initialized empty Git repository in E:/git/config/server/

e:\git\config>cd pr4

e:\git\config\pr4>git remote add server ../server

e:\git\config\pr4>git remote -v
server  ../server (fetch)
server  ../server (push)

e:\git\config\pr4>git push server master

e:\git\config\pr4>cd ..

e:\git\config>git clone server server-clone

e:\git\config>cd server-clone

e:\git\config\server-clone>git config --global user.name "coder2"

e:\git\config\server-clone>git config --global user.email "coder2@email.com"

e:\git\config\server-clone>echo "# Описание программы\nПрограмма выводит 'Hello, world!'" > readme.md

e:\git\config\server-clone>git add readme.md

e:\git\config\server-clone>git commit -m "add readme.md"

e:\git\config\server-clone>git push origin master

e:\git\config\server-clone>cd ..

e:\git\config>cd pr4

e:\git\config\pr4>git pull server master

e:\git\config\pr4>echo "\n## Авторы\n- coder1: did something" >> readme.md

e:\git\config\pr4>git add readme.md

e:\git\config\pr4>git commit -m "add info about authors"

e:\git\config\pr4>git push server master

e:\git\config\pr4>cd ..

e:\git\config>cd server-clone

e:\git\config\server-clone>git pull origin master

e:\git\config\server-clone>type readme.md
"# Описание программы\nПрограмма выводит 'Hello, world!'"
"\n## Авторы\n- coder1: did something"

e:\git\config\server-clone>git status

e:\git\config\server-clone>echo "\n- coder2 - did something too" >> readme.md

e:\git\config\server-clone>git add readme.md

e:\git\config\server-clone>git commit -m "add info abot coder2"

e:\git\config\server-clone>git push origin master
```

### log
```
e:\git\config\server-clone>git log
commit 185558e9288dd1ffbc52b70e75caf9df6e92e13c (HEAD -> master, origin/master, origin/HEAD)
Author: coder2 <coder2@email.com>
Date:   Sun Nov 10 18:41:56 2024 +0300

    add info abot coder2

commit bb682476498382b1a86a58a25cf82506abef3add
Author: coder2 <coder2@email.com>
Date:   Sun Nov 10 18:35:41 2024 +0300

    add info about authors

commit d6c6f9131357f972fb12fde9374dc9076870dded
Author: coder2 <coder2@email.com>
Date:   Sun Nov 10 18:30:44 2024 +0300

    add readme.md

commit b62537701d351206998bc2d79fc40e30487ebffa
Author: coder1 <coder1@email.com>
Date:   Sun Nov 10 18:01:28 2024 +0300

    add prog.py
```


## Задача 4
> _Написать программу на Питоне (или другом ЯП), которая выводит список содержимого всех объектов репозитория. Воспользоваться командой "git cat-file -p"_

