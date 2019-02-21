---
layout: post
title: "Some notes about language modelling"
date: 2019-02-20
---
 Language models try to understand the relations between word and the generation of sentences or sequences of words. They can be of 2 types:
 1) Conditional: where the generation or prediction is based on other previous sentences given to the model. For example, tasks such as machine translation, paraphrase.
 2) Unconditional: where the generation is done for only the next word given the previous word.

 Representation of the data is also important in any model. In language models, usually n-grams have been used. Although lately, more neural language models use word embeddings. Word embeddings are supposed to work better because they can involve some of the order of information, instead of the bag of words. They also can provide less sparsity, compared to the one-hot-encoding. The word-embedding approach was introduced by Mikolov.

 Neural Turing Machines make use of external memory resources

 Some references
 https://towardsdatascience.com/recurrent-neural-networks-the-powerhouse-of-language-modeling-d45acc50444f