---
layout: post
title:  "Kalman Filter Parameter and Model Estimation"
date:   2015-02-10 14:34:25
categories: signal processing
tags: featured
image: /assets/article_images/rocket_crash.jpg

---

#Introduction

The Kalman filters have been used in many applications such as radar
tracker, weather forecasting, autopilot and [more](http://en.wikipedia.org/wiki/Kalman_filter#Applications)
It is named after its co-inventor and developer Rudolf Kalman.

#Kalman Filter Basis

The Kalman filters using a [Markov Chain](http://en.wikipedia.org/wiki/Markov_chain)
latent state variable. The filter assumes the current state $x_k$ is related
to the previous state $x_{k-1}$ and some input variable $u_k$ referred to
as the control variable.

$$ x_k = F x_{k-1} + B u_k + w_k $$
