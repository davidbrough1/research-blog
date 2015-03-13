---
layout: post
title:  "Kalman Filter with Time Invariant Transition Matrices"
date:   2015-02-10 14:34:25
categories: signal processing
tags: featured
image: /assets/article_images/rocket_crash.jpg

---

{% include latex.html %}

#Background

The Kalman filters have been used in many applications such as radar
tracker, weather forecasting, autopilot and [more](http://en.wikipedia.org/wiki/Kalman_filter#Applications)
It is named after its co-inventor and developer Rudolf Kalman.

#Kalman Filter Basics

The Kalman filters using a [Markov Chain](http://en.wikipedia.org/wiki/Markov_chain)
latent state vector. The filter assumes the current state vector $x_k$
is related to the previous state vector $x_{k-1}$ and some input $u_k$
referred to as the control vector.

$$ x_k = F_t x_{k-1} + B_t u_k + w_k $$

$F_t$ and $B_t$ are called the transition and control-input matrices,
and relate the previous state vector and control-vector to current
state vector. In general both of these matrices can vary in time.
$w_k$ is a noise term referred to as the process noise.

The state vector is related to the observation vector $y_k$ (the data
that is observed) through the observation matrix $H$ and a noise
variable $v_k$ called the observation noise.

$$ y_k = H x_k + v_k $$

The process noise $w_k$ and the observation noise $v_k$ are assumed to
be a sample from a multinomial normal distribution zero means and
covariances of $Q$ and $R$ respectively.

$$ w_k \sim N(0, Q) $$

$$ v_k \sim N(0, R) $$

In order to get an accurate Kalman filter, the dynamics of the system
need to be understood to create correct transition matrices, and the
covariances $Q$ and $R$ need to be estimated.

#Kalman Filter Update Process

The state estimates and covariance matrix are defined as follows.

$$ \hat{x}_{k-1} = E[x_{k-1}\rvert y_0, ..., y_{k-1} ] $$

$$ P_{k-1} = E[(x_{k-1}-\hat{x}_{k-1})(x{k-1}-\hat{x}_{k-1})^T] $$

These two quantities can be estimated at time $k$ as follows

$$ \hat{x}_{k \rvert k-1} = F_t \hat{x}_{k \rvert k-1} + B_k u_k$$

$$ P_{k\rvert k-1} = E[(x_{k-1}-\hat{x}_{k-1})(x{k-1}-\hat{x}_{k-1})^T] $$

<!---
$$ a_k = a_{t\rvect k-1} + H_{k}P_{k \rvert k-1} H_{k}^T + B_k Q_k B_k^T $$
$$ P_{k}
-->

#Maximum Likelihood Estimation of Time Invarient Transition Matrices

