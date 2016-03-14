---
layout: post
title:  "Kernel PCA"
subtitle: "Simple trick for non-linear dimensionality reduction"
author: David Brough
categories: post
tags: featured
---
{% include latex.html %}

## Principal Component Analysis

Suppose we have a dataset of size
$m$ by $n$ with $m$ number of samples and $n$ number of features. If we
would like to do dimensionality reduction of the data using Principal
Component Analysis (PCA), we need to solve the following eigenvector
equations. Let's start off with some definitions.

Let, $x$ be our feature vector and our $n$ by $n$ covariance matrix $C$ be defined as

$$ C = \frac{1}{n} \sum_i x_i x_i^T $$

and the m  be defined as

$$ C q = \lambda q $$

where $q$ is an eigenvector (or principal component) and $\lambda$ is an eigenvalue.

## PCA in Terms of Inner Products
Any eigenvector $q$ can be represented in terms of
a linear combinations of features.

$$ q = \sum_i^n \beta_i x_i $$

The weights of each feature $\beta$ can be found by restating the eigenvalue
equation in terms of the features $x$.

$$ \frac{1}{n} \sum_i x_i x_i^T q = \lambda q $$

given that

$$ x_i x_i^T q = x_i^T q x_i $$

We can rearrange the eigenvalue equation into the following form.

$$ \sum_i  \frac{x_i^T q}{n \lambda}  x_i =  q $$

or

$$ q = \sum_i  \beta_i   \phi(x_i)$$

$$ \beta_i  = \frac{x_i^T q}{n \lambda}$$

Now that we have established that relationship between eigenvectors
and features let's rewrite the eigenvalue equation again, but this time
completely interns of $x$ and $\beta$.

$$ \frac{1}{n} \sum_i x_i x_i^T \sum_j  \beta_{ij}   x_j = \lambda \sum_l  \beta_{l} x_l $$


$$ \sum_i x_i  \sum_j  \beta_{ij}  x_i^T x_j = n \lambda \sum_l  \beta_{l}   x_l $$

Additionally we can apply any combinations of features $x_k$ and the following equation holds.

$$ \sum_i x_k^T x_i  \sum_j  \beta_{ij}  x_i^T x_j = n \lambda \sum_l \beta_{l} x_k^T x_l $$

The same equation in matrix form looks like

$$ K^2 \beta = n \lambda K \beta$$

where

$$ K = k(x_k, x_i) =  x_k^T x_i \beta$$

This equation can be reduced to

$$ K \beta = n \lambda \beta$$

We know have an equation that is similar to the eigenvalue equation
that we started with. Our $n$ by $n$ covariance matrix $C$ has been replaced by
our $m$ by $m$ kernel matrix $K$ and our eigenvectors $q$ have been replaced by
$\beta$.

## Kernel Functions

Doing dimensionality reduction with our new version of our eigenvalue equation (as defined so far)
would provide the same result as regular PCA and in fact is Kernel PCA with a linear kernel.
We can get a non-linear dimensionality reduction by introduction
a function $\phi(x)$ in our definitions of $K$ and $\beta$.


$$ \beta_i  = \frac{\phi(x_i)^T q}{n \lambda}$$

$$ K = k(\phi(x_k), \phi(x_i)) =  \phi(x_k)^T \phi(x_i)$$

The kernel function $k(\phi(x_k), \phi(x_i))$ can be used to create a global non-linear
transformation of our features $x$. Now the question is what constraints
are there on $\phi$ and $K$? The function $k(\phi(x_k), \phi(x_i))$ must
make our kernel matrix $K$ positive semi-definite

$$ v^T K v \geq 0 $$

where $v$ is any vector.

<!-- Some typical kernels in include

|            |      $k(x_k, x_i)$ |
|------------|-------------------:|
| Polynomial | $x_k^T x_i + c)^d$ | -->

