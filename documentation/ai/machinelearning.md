---
layout: default
title: Machine Learning
---

# Machine Learning

Various methods:

## Neural Network

Started with Perceptron but could not be trained because the activation function was not differentiable. Research guided to make it differentiable but then some problem like XOR could not be solved. This was resolved by using more than one layer. Back propagation algorithm was developed to train such deeper nns.

Learning can be done in various ways:

  1. Stochastic Gradient Descent - Run on training example one by one
  2. Batch Gradient Descent - Run it on whole data set in a single execution
  3. Mini Batch Gradient Descent - Divide the entire training set into mini batches or around 50-300 and run on them one by one.

  Each run is called an epoch. At every run we try to recalculate the gradient and the loss function. Generally the learning rate is manually adjusted but following can be used to automatically adjust it - Adam optimizer, AdaGrad and RMSProp.

## Random Forest

## Decision Tree

## Linear Regression

## Others
