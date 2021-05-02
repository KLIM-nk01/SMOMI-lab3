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


![image](https://user-images.githubusercontent.com/56519328/116051585-6b880380-a681-11eb-8f16-07aee4705635.png)

**Графики обучения нейронной сети EfficientNet-B0(предварительно обученную на базе изображений imagenet), фиксированный темп обучения 0.01**
![image](https://user-images.githubusercontent.com/56519328/116607263-715c3e00-a93a-11eb-85d3-4648ed243ccd.png)
![image](https://user-images.githubusercontent.com/56519328/116607335-846f0e00-a93a-11eb-8182-1e7264ba8277.png)

**Графики обучения нейронной сети EfficientNet-B0(предварительно обученную на базе изображений imagenet), фиксированный темп обучения 0.001**
![image](https://user-images.githubusercontent.com/56519328/116607365-905ad000-a93a-11eb-975d-75906e1cd5ba.png)
![image](https://user-images.githubusercontent.com/56519328/116607409-a072af80-a93a-11eb-9822-e3e74b465d6c.png)

**Графики обучения нейронной сети EfficientNet-B0(предварительно обученную на базе изображений imagenet), фиксированный темп обучения 0.0001**
![image](https://user-images.githubusercontent.com/56519328/116607459-b08a8f00-a93a-11eb-828c-1a184ecf4873.png)
![image](https://user-images.githubusercontent.com/56519328/116607514-c009d800-a93a-11eb-95ae-a60563aede79.png)




**Реализовать и применить в обучении следующие политики изменения темпа
обучения, а также определить оптимальные параметры для каждой политики:
a. Косинусное затухание (Cosine Decay)**

***График метрики точности:***
![image](https://user-images.githubusercontent.com/56519328/116806456-ca43f600-ab35-11eb-85d8-dfe48f2b8490.png)
![image](https://user-images.githubusercontent.com/56519328/116806459-d16b0400-ab35-11eb-90f5-6e8513cc6f9b.png)


***График функции потерь:***
![image](https://user-images.githubusercontent.com/56519328/116806472-e34ca700-ab35-11eb-93c5-339967b5cb71.png)
![image](https://user-images.githubusercontent.com/56519328/116806476-e9db1e80-ab35-11eb-985b-a2e131ee2fc3.png)
 
 **Графики темпов обучения**
 ![image](https://user-images.githubusercontent.com/56519328/116806508-26a71580-ab36-11eb-9ac8-7906599e08de.png)
![image](https://user-images.githubusercontent.com/56519328/116806516-30c91400-ab36-11eb-8102-d326914a17d7.png)
![image](https://user-images.githubusercontent.com/56519328/116806526-3f173000-ab36-11eb-87f8-96ed14bd62c6.png)



**Графики обучения нейронной сети EfficientNet-B0 c использованием техники обучения Transfer Learning**


  
***График метрики точности:***

***График функции потерь:***


***Анализ полученных результатов***

