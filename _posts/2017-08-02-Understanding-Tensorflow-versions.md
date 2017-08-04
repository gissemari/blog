---
layout: post
title: "Understanding Tensorflow versions"
date: 2017-08-02
---

Empezaré diciendo que el hecho de encontrar diferentes ejemplos en Tensorflow se debe no sólo a la creación de nuevas versiones sino también a dos niveles diferentes de uso. Cuando empecé con Tensorflow encontré más ejemplos de "bajo nivel". Si bien TensorFlow ya envuelve la creación y operación entre vectores y matrices, el bajo nivel que describo aquí se relaciona a los legos con que podemos jugar para constuir la arquitectura de Deep Learning que deseemos. Meses después al buscar ejemplos de otras arquitecturas (para predicción por ejemplo) encuentro más páginas, blogs, etc. del uso del API de TensorFlow que es a su vez un nivel más alto de abstracción que permite combinar bloques más grandes de legos (ya definidos).
Además de el alto nivel de abstracción que nos provee con el módulo tensorflow.contrib, más conocido como learn, existen varias librerías que encapsulan aún más su uso. Tales son tflearn, polyaxon, etc.

Por otro lado, una de las funcionalidades que buscaba para indicar el tamaño del batch para cada etapa (train, evaluate, predict) no aparecía en muchos ejemplos. Por fin, el Yuan Tang's blog [here](http://terrytangyuan.github.io/2016/06/09/scikit-flow-v09/) me mostró cómo.
