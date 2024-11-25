## Задача 1
> Написать программу на Питоне, которая транслирует граф зависимостей civgraph в makefile в духе примера выше. Для мало знакомых с Питоном используется упрощенный вариант civgraph.

```
import json


def generate_makefile(graph):
    makefile_lines = []
    for target, dependencies in graph.items():
        dep_str = " ".join(dependencies)
        makefile_lines.append(f"{target}: {dep_str}")
        makefile_lines.append(f'\t@echo "Researching {target}."')
        makefile_lines.append("")

    return "\n".join(makefile_lines)

with open("civgraph.json", "r") as f:
     civgraph = json.load(f)

makefile_content = generate_makefile(civgraph)


with open("Makefile", "w") as f:
    f.write(makefile_content)

```
<img width="490" alt="image" src="https://github.com/user-attachments/assets/67bbda35-40af-4f67-9dda-02149213b2ea">

## Задача 2
> Реализовать вариант трансляции, при котором повторный запуск make не выводит для civgraph на экран уже выполненные "задачи".

Основное изменение - введение touch для обеспечения единственности выполнения. Если .done файлы уже существуют, make пропустит выполнение этих задач.

```
import json

def generate_makefile(graph):
    makefile_lines = []
    for target, dependencies in graph.items():
        dep_files = [f"{dep}.done" for dep in dependencies]
        dep_str = " ".join(dep_files)
        makefile_lines.append(f"{target}.done: {dep_str}")
        makefile_lines.append(f'\t@echo "Researching {target}."')
        makefile_lines.append(f"\ttouch {target}.done")
        makefile_lines.append("") 

    return "\n".join(makefile_lines)



with open("civgraph.json", "r") as f:
    civgraph = json.load(f)

makefile_content = generate_makefile(civgraph)

# Сохранение результата в файл Makefile
with open("Makefile", "w") as f:
    f.write(makefile_content)

print("Makefile сгенерирован.")

```
