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

![image](https://github.com/user-attachments/assets/cc0f46f1-4c53-438c-9856-83c3935fcf6a)

```PlantUML
@startuml
actor "Студент Спесивцева А.А." as Student
database "Piazza" as Piazza
actor "Преподаватель" as Teacher

Teacher -> Piazza: Публикация задачи
activate Piazza
Piazza -> Teacher: Задача опубликована
deactivate Piazza

Student -> Piazza: Поиск задач
activate Piazza
Piazza -> Student: Получение задачи
deactivate Piazza

Student -> Piazza: Публикация решения
activate Piazza
Piazza -> Student: Решение опубликовано
deactivate Piazza

Teacher -> Piazza: Поиск решений
activate Piazza
Piazza -> Teacher: Решение найдено
Teacher -> Piazza: Публикация оценки
Piazza -> Teacher: Оценка опубликована
deactivate Piazza

Student -> Piazza: Проверка оценки
activate Piazza
Piazza -> Student: Оценка получена
deactivate Piazza
@enduml
```
