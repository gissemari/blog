---
layout: post
title: "Understanding Tensorflow versions"
date: 2017-08-02
---

I will start saying that the fact of someone finding so many Tensorflow projects is due not only to the new version releases but to two levels of use. When I started learning Tensorflow I found more examples of the "lower" level. Although it's true that Tensorflow wraps the definition and operations between vectors and matrices, the lower level to which I refer to is the one that allows us to play with blocks in order to build a deep learning architecture. Some time later, while looking for prediction examples, I found more information about TFLearn, a Tensorflow higher-level API. This is the "upper" level that allow us to build larger blocks related more with more exact models like Feed Forwards, CNN or RNN. Also it standarize the usual machine learning library functionalities like fit, generate and evaluate.

There are some other high-level approaches like the Tensorflow module contrib (tensorflow.contrib), also known as learn, and some other libraries like polyaxon. However, I must say that I could not find some functionalities like setting a different size of batch for each epoch. I finally found some hints that I haven't used yet from Yan Tang's blog [here](http://terrytangyuan.github.io/2016/06/09/scikit-flow-v09/)(section TensorFlow DataFrame). 

