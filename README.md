# ADGD_URFU_5
Workshop #5

# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Иванов Денис Александрович
- РИ-230941

Отметка о выполнении заданий:
| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

## Цель работы
Познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.
 
### Поиск агентом объекта на сцене
Ход работы:
- Создали новый проект и добавили туда все необходимые ассеты.
- С помощью Anaconda prompt установили все необходимые пакеты для обучения.
- Добавили скрипт RollerAgent и запустили обучение.

![Снимок экрана 2024-12-20 202645](https://github.com/user-attachments/assets/fa16b329-c161-4a64-bf9f-ea3a3a5f45e9)

- Изначально шары катятся в случайные направления, затем пытаются катиться в сторону таргета. На примерно 20000-30000 шагах, шар начинает довольно уверенно преследовать цель.

### Симулятор добычи ресурсов
Ход работы:
- Скачали и запустили проект Unity ML-Agent_EconomicModel.
- Так же запустили тренировку ML-агентов. 

![Снимок экрана 2024-12-20 235846](https://github.com/user-attachments/assets/50c9e94a-cb65-4bb4-a54d-82b8f080b055)

- Установили Tensor для построения графиков и оценки результата.

![Снимок экрана 2024-12-20 235937](https://github.com/user-attachments/assets/a75012a9-19e3-45d6-9ee2-aea9eb8c6abc)

## Задание 1
### Найдите внутри C# скрипта “коэффициент корреляции” и сделать выводы о том, как он влияет на обучение модели.

- Внутри скрипта Move есть переменная tempInf, которая определяет порог инфляции. Если агент не позволяет инфляции подняться выше порога (в нашем случае 6%), он получает положительное вознаграждение, иначе отрицательное. То есть tempInf является критерием успеха и тогда, чем он выше, тем проще получить вознаграждение и наоборот.

## Задание 2
###  Изменить параметры файла yaml-агента и определить какие параметры и как влияют на обучение модели. Привести описание не менее трех параметров.

- learning_rate: влияет на скорость обучения агента. Но при высоких показателях агент начинает обучаться некорректно, а при более низких, чем установлено по стандарту, обучение происходит очень медленно.
- epsilon: влияет на "стабильность" изменения поведения. На больших значениях агент резче меняет поведение, на более низких - реже.
- max_steps: максимальное количество шагов, которое сделает ML-агент. При низких значениях он не успевает обучиться. 

## Задание 3
###  Приведите примеры, для каких игровых задачи и ситуаций могут использоваться примеры 1 и 2 с ML-Agent’ом. В каких случаях проще использовать ML-агент, а не писать программную реализацию решения?

- ML-агента лучше использовать в ситуациях, когда мы имеем дело со сложным и/или изменяющимся окружением. Например, если в каждой итерации цель меняет положение/меняется экономика/появляются новые "препятствия". ML-агенты могут адаптироваться к таким изменениям.

## Выводы

Познакомились с программными средствами для обучения ML-агентов. Разобрались в каких случаях их стоит применять и как различные параметры yaml-агента влияют на его обучение.
