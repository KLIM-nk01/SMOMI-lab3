# Лабораторная работа 3.

**Цель лабораторной работы:**  Исследовать влияние параметра “темп обучения” на
процесс обучения нейронной сети на примере решения задачи классификации Food-101 с
использованием техники обучения Transfer Learning

**Задачи:**

1. С использованием [1] и техники обучения Transfer Learning обучить нейронную сеть
EfficientNet-B0 (предварительно обученную на базе изображений imagenet) для
решения задачи классификации изображений Food-101 с использованием
фиксированных темпов обучения 0.01, 0.001, 0.0001
2. Реализовать и применить в обучении следующие политики изменения темпа
обучения, а также определить оптимальные параметры для каждой политики:
a. Косинусное затухание (Cosine Decay) [2,4]
b. Косинусное затухание с перезапусками (Cosine Decay with Restarts) [3,4]

<hr/>

## Графики обучения нейронной сети EfficientNet-B0(предварительно обученную на базе изображений imagenet), фиксированный темп обучения 0.01, 0.001, 0.0001 ##


***График метрики точности (валидационные данные):***
![image](https://user-images.githubusercontent.com/56519328/116857070-dba80380-ac04-11eb-8f6f-6d2324459e95.png)

***График функции потерь (валидационные данные):***
![image](https://user-images.githubusercontent.com/56519328/116857707-ec0cae00-ac05-11eb-84eb-de0f31d7e606.png)

***График метрики точности (тренировочные данные):***
![image](https://user-images.githubusercontent.com/56519328/116857553-abad3000-ac05-11eb-94f2-d10d81e55ca4.png)

***График функции потерь (тренировочные данные):***
![image](https://user-images.githubusercontent.com/56519328/116857680-e1521900-ac05-11eb-8185-f91f032691fd.png)


***Анализ полученных результатов***
Анализируя полученные графики для первой задачи, можно утверждать, что оптимальным параметром фиксированного темпа обучения для нейронной сети EfficientNet-B0 (предварительно обученную на базе изображений imagenet) для решения задачи классификации изображений Food-101, является параментр равный 0.0001, так как наибольшая точность на графике точности для валидационных данных - 67%, достигнута именно с этим параметром, а так же наименшее значение на графике функции  потерь - 1.209.

<hr/>

## Реализовать и применить в обучении следующие политики изменения темпа обучения, а также определить оптимальные параметры для каждой политики: a. Косинусное затухание (Cosine Decay) 

```python
tf.keras.experimental.CosineDecay(initial_learning_rate, decay_steps)
```

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/116806456-ca43f600-ab35-11eb-85d8-dfe48f2b8490.png)
![image](https://user-images.githubusercontent.com/56519328/116806459-d16b0400-ab35-11eb-90f5-6e8513cc6f9b.png)


***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/116806472-e34ca700-ab35-11eb-93c5-339967b5cb71.png)
![image](https://user-images.githubusercontent.com/56519328/116806476-e9db1e80-ab35-11eb-985b-a2e131ee2fc3.png)


 **Графики темпов обучения**
 <hr/>
 
![image](https://user-images.githubusercontent.com/56519328/116860249-f3ce5180-ac09-11eb-885d-8c1a3578b52d.png)

<hr/>


 
![image](https://user-images.githubusercontent.com/56519328/116892495-8d145c80-ac38-11eb-8904-f9cc008e89b3.png)

<hr/>



![image](https://user-images.githubusercontent.com/56519328/116891798-d44e1d80-ac37-11eb-9c1a-b7ab0d330495.png)

<hr/>

***Анализ полученных результатов***
В ходе выполнения 3а задачи для политики Cosine Decay, я изменял параметры initial_learning_rate и decay_steps, получились следующие наборы параметров: 

![image](https://user-images.githubusercontent.com/56519328/116862273-2f1e4f80-ac0d-11eb-8c31-60649e886a98.png)

где первый параметр initial_learning_rate а второй соответсвенно decay_steps. Анализируя полученные графики, могу утверждать, что оптимальными параметрами для политики Cosine Decay из приведенных выше параметров, являются параметры initial_learning_rate = 0.001 и decay_steps = 30000, так как на графике точности для валидационных данных была достигнута наибольшая точность равная 67% и наименьшее значение функции потерь - 1.214

<hr/>
 
## Реализовать и применить в обучении следующие политики изменения темпа обучения, а также определить оптимальные параметры для каждой политики:  b. Косинусное затухание с перезапусками (Cosine Decay with Restarts)

 ```python
tf.keras.experimental.CosineDecayRestarts(initial_learning_rate, first_decay_steps, t_mul, m_mul)
```
***График метрики точности (валидационные данные):***
 ![image](https://user-images.githubusercontent.com/56519328/116874576-36038d00-ac22-11eb-8cc7-a4845d04174f.png)

***График функции потерь (валидационные данные):***
![image](https://user-images.githubusercontent.com/56519328/116874725-72cf8400-ac22-11eb-97e4-1e9e22c50094.png)

***График метрики точности (тренировочные данные):***
![image](https://user-images.githubusercontent.com/56519328/116874653-54698880-ac22-11eb-9ede-b8b2e9f07a68.png)

***График функции потерь (тренировочные данные):***
![image](https://user-images.githubusercontent.com/56519328/116874875-b1fdd500-ac22-11eb-8585-3e72fa40bac3.png)

 **Графики темпов обучения**
![image](https://user-images.githubusercontent.com/56519328/116874824-9b577e00-ac22-11eb-882a-f3f0174e34cf.png)


***Анализ полученных результатов***
в ходе работы изменялись параметры initial_learning_rate, first_decay_steps, t_mul, m_mul:

![image](https://user-images.githubusercontent.com/56519328/116875584-d5754f80-ac23-11eb-99f3-619e0ec60970.png)

где первый параметр -  initial_learning_rate, второй - first_decay_steps, третий - t_mul, четвертый - m_mul.
Анализируя полученые графики точности (валидационные данные) для политики Cosine Decay with Restarts, можно сказать что наибольшая точность была достигнута в 12 эпохе, точность равна 67%, для сети с параметрами 0.001 - 10000 - 2.0 - 1.0, однако уже с 13 эпохи сеть с данными параметрами начала переобучаться, что подтверждает график функции потерь (начал возрастать). Анализируя графики для сетей с другими параметрами можно сказать, что наиболее оптимальными параметрами для политики Cosine Decay with Restarts, является набор параметров 0.0001 -  10000 - 1.0 - 1.0. График точности для сети с данными параметрами составил в конечном итоге 67%, а график функции потерь показал наименьшее значение равное 1.24.

Вывод: в ходе выполнения лабораторной работы, я определил оптимальные параметры для каждой из политик изменения темпа
обучения. Сравнив результаты всех политик изменения темпа обучения, могу утверждать, что для моих экспериментов лучшей политикой является политика Косинусного застухания, так как точность с оптимальными параметрами,initial_learning_rate = 0.001 и decay_steps = 30000,  составила 67,8% и значение потерь - 1.209,  а для политики Косинусного затухания с перезапусками составила 67,1% и потерь - 1.214 с параметрами initial_learning_rate = 0.0001, first_decay_steps = 10000  t_mul =  1.0, m_mul = 1.0. 

