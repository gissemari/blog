---
layout: post
title: "Key topics from other papers for energy disaggregation"
date: 2017-12-28
---

VAE
- Perform maximum likelihood (ML) or maximum a posteriori (MAP) inference on (global) parameters and variational inference on the latent variables.
- When a neural network is used for the recognition model, we arrive at the variational auto-encoder.
- Interested in general algorithm that works efficiently in the case of Intractability (for the marginal likelihood p(x), p(x|z) e.g neural nets with nonlinear hidden layer) and large dataset (to perform minibatch instead of batch or single point optimization).
- Three related problems solved: 1) ML estimation for parameters theta (note that this and marginal likelihood are different). 2) Approximate posterior inference of the latent variable z given x. 3) Approximate marginal inference of x
- We'll introduce a method for learning the recognition model parameters phi jointly with the generative model parameters theta.
- Then it is obvious that L is a lower bound of the log probability of the observations. As a result, if in some cases we want to maximize the marginal probability, we can instead maximize its variational lower bound L. [Variational Bound](http://legacydirs.umiacs.umd.edu/~xyang35/files/understanding-variational-lower.pdf) 