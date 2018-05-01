---
layout: post
comments: true
title: "TensorFlow - Flujo de operaciones con tensores"
date: 2018-04-21 19:18:28 +0100
categories: jekyll update
---
> Desde que Google la liberó como software de código abierto en 2015,
> TensorFlow se ha convertido en la biblioteca más popular para
> resolver problemas de machine learning.

# Cómo funciona TensorFlow

Cuando se habla de _machine learning_ o aprendizaje automático lo habitual es pensar en redes neuronales artificiales.
En realidad, existe una gran variedad de técnicas de aprendizaje automático además de las redes neuronales, por ejemplo
los muy interesantes algoritmos genéticos, pero es cierto que son las redes neuronales la más extendida en su uso por
su alto rendimiento en el aprendizaje.

Con [TensorFlow][tensorflow] es posible implementar algoritmos que se comportan o resuelven problemas de aprendizaje
automático como lo haría una red neuronal, pero no es un sistema en el que podamos crear redes de neuronas, sino que la
biblioteca es capaz de implementarlas mediante operaciones con arrays multidimensionales -tensores-.

Los datos en TensorFlow pueden ser un tensor de orden 0 -un escalar-, un tensor de orden 1 -un vector- o un tensor de
orden 2 -una matriz-; y estos operan entre ellos y se propagan a través de un grafo dirigido. **Todo lo que hace**
**TensorFlow es componer un grafo de operaciones matriciales cuyos resultados siguen un flujo concreto hasta obtener**
**los datos de salida.**

Para ver el funcionamiento de esto, vamos a utilizar como ejemplo una sencilla red de neuronas artificiales compuesta
por tres valores de entrada, una única capa oculta de dos neuronas y una neurona de salida:

![Red neuronal de ejemplo](/images/2018-04-21/red-neuronal-ejemplo.png)

En TensorFlow, los datos de entrada de este ejemplo estarían representados como un vector fila de dimensión 1x3, es
decir, una matriz de una única fila como la siguiente: `[E0 E1 E2]`. Estos datos de entrada serán transformados a
medida que "viajan" por las distintas capas de la red.

Las aristas en este grafo se corresponden con los pesos sinápticos. TensorFlow los representa mediante las matrices (1)
y (2) como se ve en la siguiente imagen. Sabemos que los datos de entrada de una neurona artificial en una capa son los
datos de salida de la capa anterior y los datos de salida serán los datos de entrada de la capa siguiente y que el
valor de salida de una neurona es el sumatorio de sus entradas multiplicadas cada una por su peso correspondiente.
Solamente hay que multiplicar el vector de entradas de cada capa por estas matrices de pesos para obtener el vector de
entradas de la capa siguiente.

![Matrices de pesos](/images/2018-04-21/matrices-pesos.png)

Multiplicar el vector de entrada de dimensión 1x3 por la matriz de pesos (1) de dimensión 3x2 da como resultado el
vector de dimensión 1x2 `[N0 N1]` con los valores de las neuronas de la capa oculta. De la misma manera, multiplicar
este vector por la matriz de pesos (2) de dimensión 2x1 da como resultado el escalar `[S]`, correspondiente al valor de
salida de la red neuronal.

![Operaciones](/images/2018-04-21/operaciones.png)

Los valores de las matrices de pesos (1) y (2) irán actualizándose durante el entrenamiento con el objetivo de
minimizar el error obtenido, al igual que a los tensores resultantes de realizar estas operaciones se les aplica la
función de activación correspondiente. Así, con todas estas operaciones se implementa un algoritmo que entrena como lo
haría una red neuronal.

Una de las ventajas de esta forma de implementar algoritmos de _machine learning_ es que puedes construir soluciones a
problemas complejos en un único fichero de forma secuencial mediante operaciones sin necesidad de definir modelos,
clases ni una una estructura compleja de proyecto. Limpio, fácil y rápido. Esto permite centrarse en el entrenamiento
sin perder mucho tiempo en la implementación. Además, más allá de las neuronas artificiales, este sistema permite a
TensorFlow implementar cualquier solución de aprendizaje automático que pueda ser modelizado en operaciones.

Pero el principal potencial de TensorFlow es que estas operaciones son paralelizables, por lo que podríamos ejecutar
nuestra solución en un clúster y aprovechar así las grandes capacidades de cómputo de las que dispongamos e implementar
_deep learning_.

[tensorflow]: https://www.tensorflow.org/