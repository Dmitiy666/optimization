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
при обучении модели по зашумлённой или нерегулярной функции потерь,
так как RMSProp сглаживает краткосрочные колебания и выделяет долгосрочные
тренды, что помогает снизить влияние шума и быстрее сходиться модели.

SGD может быть полезен, если данные огромны,
а время вычислений является важным фактором, 
так как он лучше обобщает данные за счёт низкой скорости вычислений

# Задание №3
Оптимизация гиперпараметров с помощью optune.

Датасет FashionMnist был заменен на датасет CIFAR-10

Вывод консоли:
    Study statistics: 
    Number of finished trials: 47 
    Number of pruned trials: 29 
    Number of complete trials: 18 
Best trial: 
    Value: 0.5453125 
    Params: dropout: 0 optimizer: Adam lr: 0.003354162221602514


# Задание №4

Оптимизация модели с помощью библиотеки onnx.

Необходимо конвертировать модель в onnx и сравнить производительность (скорость и точность) с model.pth.

Результаты работы torch модели:

Accuracy for class: plane is 54.9 %
Accuracy for class: car   is 33.0 %
Accuracy for class: bird  is 20.4 %
Accuracy for class: cat   is 27.8 %
Accuracy for class: deer  is 38.9 %
Accuracy for class: dog   is 45.4 %
Accuracy for class: frog  is 56.1 %
Accuracy for class: horse is 73.7 %
Accuracy for class: ship  is 62.3 %
Accuracy for class: truck is 78.6 %
Time, ms:  0.4050048828125

Результат работы onnx модели:

Accuracy for class: plane is 54.9 %
Accuracy for class: car   is 33.0 %
Accuracy for class: bird  is 20.4 %
Accuracy for class: cat   is 27.8 %
Accuracy for class: deer  is 38.9 %
Accuracy for class: dog   is 45.4 %
Accuracy for class: frog  is 56.1 %
Accuracy for class: horse is 73.7 %
Accuracy for class: ship  is 62.3 %
Accuracy for class: truck is 78.6 %
Time, ms:  0.43108396530151366