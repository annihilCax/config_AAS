## Задача 1
> _Реализовать с помощью математического языка LaTeX нижеприведенную формулу:_

<img width="800" alt="image" src="https://github.com/user-attachments/assets/04bcbd1d-a2b1-4332-863c-f2b16c3f092c">


--
```Latex
\newcommand\myeq{\mathrel{\overset{\makebox[0pt]{\mbox{\normalfont\tiny\sffamily (u=t^{-2m})}}}{=}}}

 \[ \int_{x}^{\infty} \frac{dt}{t(t^2-1)\log t} = \int_{x}^{\infty} \frac{1}{t\log t} (\sum_{m} t^{-2m}) dt = \sum_{m} \int_{x}^{\infty} \frac{t^{-2m}}{t\log t}dt \quad \myeq \quad - \sum_{m} \operatorname{li}(x^{-2m})\]
```

## Задача 2
>На языке PlantUML реализовать диаграмму на рисунке ниже. Прислать текст на PlantUML и картинку-результат, в которой ФИО студента заменены Вашими собственными. Обратите внимание на оформление, желательно придерживаться именно его, то есть без стандартного желтого цвета и проч. Чтобы много не писать используйте псевдонимы с помощью ключевого слова "as".

<img width="450" alt="image" src="https://github.com/user-attachments/assets/1c84ce8a-784d-4d1a-a030-3c8f2f9bc71c">


```PlantUML
@startuml
skinparam monochrome true
actor "Студент Спесивцева А.А." as Студент
database "Piazza"
actor "Преподаватель"

Преподаватель -> Piazza: Публикация задачи
activate Piazza
Piazza --> Преподаватель: Задача опубликована
deactivate Piazza

Студент -> Piazza: Поиск задач
activate Piazza
Piazza --> Студент: Получение задачи
deactivate Piazza

Студент -> Piazza: Публикация решения
activate Piazza
Piazza --> Студент: Решение опубликовано
deactivate Piazza

Преподаватель -> Piazza: Поиск решений
activate Piazza
Piazza --> Преподаватель: Решение найдено
Преподаватель -> Piazza: Публикация оценки
Piazza --> Преподаватель: Оценка опубликована
deactivate Piazza

Студент -> Piazza: Проверка оценки
activate Piazza
Piazza --> Студент: Оценка получена
deactivate Piazza
@enduml
```
