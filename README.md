# Optimize computer vision models

Практика по курсу "Оптимизация моделей компьютерного зрения"  


# Задание №2

Главным заданием было сравнить сходимость двух алгоритмов 

SGD и RMSprop

По графику видно, что RMSproup справился лучше, так как ошибка (loss)
у него меньше. 

![loss_plot_SGD.png](loss_plot_SGD.png)

![loss_plot_RMSprop.png](loss_plot_RMSprop.png)

RMSProp может быть предпочтительнее в следующих случаях:
при обучении модели с множеством параметров, если возникают проблемы 
с расходимостью или колебаниями во время обучения; 
если сложно настроить скорость обучения, 
так как RMSProp масштабирует градиенты, 
что помогает процессу оптимизации более плавно сходиться независимо 
от скорости обучения.
При обучении модели по зашумлённой или нерегулярной функции потерь,
так как RMSProp сглаживает краткосрочные колебания и выделяет долгосрочные
тренды, что помогает снизить влияние шума и быстрее сходиться модели.

SGD может быть полезен, если данные огромны,
а время вычислений является важным фактором, 
так как он лучше обобщает данные за счёт низкой скорости вычислений

# Задание №3
Оптимизация гиперпараметров с помощью optune.

Датасет FashionMnist был заменен на датасет CIFAR-10

Поиск должен был осуществляться по данным гиперпараметра:
("dropout", 0.2, 0.5) ; ("lr", 1e-5, 1e-1, log=True)

Вывод консоли:
Study statistics:

• Number of finished trials: 47

• Number of pruned trials: 29

• Number of complete trials: 18

Best trial:

• Value: 0.5453125

• Params:

  • dropout: 0

  • optimizer: Adam

  • lr: 0.003354162221602514

# Задание №4

## Результаты работы Torch модели

| Класс  | Точность (%) |
|--------|--------------|
| Plane  | 54.9         |
| Car    | 33.0         |
| Bird   | 20.4         |
| Cat    | 27.8         |
| Deer   | 38.9         |
| Dog    | 45.4         |
| Frog   | 56.1         |
| Horse  | 73.7         |
| Ship   | 62.3         |
| Truck  | 78.6         |

**Время выполнения:** 0.5348 ms

## Результаты работы ONNX модели

| Класс  | Точность (%) |
|--------|--------------|
| Plane  | 54.9         |
| Car    | 33.0         |
| Bird   | 20.4         |
| Cat    | 27.8         |
| Deer   | 38.9         |
| Dog    | 45.4         |
| Frog   | 56.1         |
| Horse  | 73.7         |
| Ship   | 62.3         |
| Truck  | 78.6         |

**Время выполнения:** 0.4311 мс

Модель onnx предсказывает в 1.4 раза быстрее 
Точность у обеих моделей идентична, отсюда следует вывод, что конвертация
моделей прошла успешно.