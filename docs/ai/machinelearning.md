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

## Linear Regression

## Others

## Bayesian Network

Probability of a feature based on other features

1. If the probabilities are independent then it forms Naive Bayes classifier

## Decision Tree

Just like the name, you are following the path of a tree and each node is a condition deciding the path.

## Logistic regression

When the data points are put on the graph and the data can be separated by a line. A new point can be seen on which region it falls on.

uses a log-loss function - large value to incorrectly classified points and a low one to correctly classified values.

Neural network is same as Logistic regression but when the regions cannot be separated by a single line but is more complex. May be two lines.

## Support vector machine

Same as Logistic regression but where you maximize the distance using linear optimization

Good Link - https://www.youtube.com/watch?v=IpGxLWOIZy4

## K Means Clustering

1. There are multiple group of clusters and we want to find center of each of those clusters.
2. Algorithm can't eye ball and find approx center.
3. So put random points anywhere - one for each cluster
4. For each point check to which random point it is located to. To which ever it is closest, assign that point that random point.
5. Then move that random point to the center of all points which are assigned that random point.
6. Keep doing this and finally you will find center points of all clusters and in the process also find the clusters.


## Hierarchical Clustering

1. Take the two closet points and make them a group
2. Keep doing this until the new group's members are already part of some other group
3. If so then merge the two groups.
4. Stop when the distance between two groups is more than the predefined distance which should not be allowed
