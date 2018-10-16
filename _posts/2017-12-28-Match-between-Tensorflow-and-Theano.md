---
layout: post
title: "Similarities and differences between Tensorflow and Theano"
date: 2017-12-28
---

Both framework have different ways to define the inputs of a model. While Tensorflow does it with placeHolder(shape), Theano does it with T.ftensor2, ftensor3 or so.
Other big difference is the dot multiplication. While in Tensorflow both x and W have to be of 2-D, Theano allows 3-D and 2-D inputs.
 [code.org](https://code.org/) 