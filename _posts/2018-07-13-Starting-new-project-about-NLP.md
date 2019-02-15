---
layout: post
title: "Starting a new project in NLP"
date: 2018-06-22
---

After finishing my project about energy disaggregation and VRNN, we had the idea to continue working with latent variables. My advisor mentioned the additional significance that latent variables can have among semantic tasks sush as intention, opinion or style recognition/generation. So I started a new adventure by searching for the state of the art. When I start a new exploration of the related literature of some topic I love to report it in an excel. I start with the usual fields like Title, Author, Conference and Year. In a NLP topic, specially approaching it with deep learning and latent variables in the 2010s, I guess the year plays an important role because this field is developing very fast. Other fields that I add are Task/Problem, Datasets and Baselines. These fields give me ideas against what works I want to measure my own work.

Some interesting tasks that I identify were dialogue generation. Basicaly this task can have 2 big approaches. Task-oriented (or goal-oriented) and open one. The first one tries to be more effective in following instructions and maybe confirming them. The second one I found more interesting because it allows more variability, randomness and really test a model in the way it can start, hold and end a conversation. 

(update 2018-09-01)
After reading about sequence-to-sequence (seq2seq) models, I decided to try to do something with the representation of certain words in the sentences. I want to understand why and how some sentences can have similar words but different meanings and the other way around, have different words but similar meanings (paraphrasing). I decided to continue using variational components in the models and I found interesting works, as RNN-VAE, RNN-VAE and SC-LSTM.

(update 2019-02-15)
Another path to research on is deep generative models for sequential data which applies for language model generation. MaskGAN can be a good start point for this. I was trying to adapt VRNN to them but haven't finished yet. Another option is GANs, that until now haven't worked that well yet, specially because of the non-differentiability of the output. Apart from the mode collapsing and training instability problems. I tried to approach the first problem by treating everything as embeddings (the outputs) but Liam Fedus told me there were some works that tried that and haven't had good results yet, nothing published about it.