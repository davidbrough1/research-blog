---
layout: post
title:  "Kalman Filter Parameter and Model Estimation"
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
latent state vector. The filter assumes the current state vector $x_k$ is related
to the previous state vector $x_{k-1}$ and some input $u_k$ referred to
as the control vector.

$$ x_k = F x_{k-1} + B u_k + w_k $$

$F$ and $B$ are called the transition and control-input matrices and
relate the previous state vector and control-vector to current
state vector. $w_k$ is a noise term referred to as the process noise.

The state vector is related to the observation vector $y_k$ (the data that
is observed) through the observation matrix $H$ and a noise variable $v_k$
called the observation noise.

$$ y_k = H x_k + v_k $$

The process noise $w_k$ and the observation noise $v_k$ are assumed to be
a sample from a multinomial normal distribution zero means and covariances
of $Q$ and $R$ respectively.

