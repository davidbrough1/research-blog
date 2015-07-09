---
layout: post
title:  "Microstructure Time Series Analysis"
subtitle: "Time Series Analysis of Low Dimensional Microstructure Descriptors"
author: David Brough
categories: post
---
{% include latex.html %}


###**Time Series Models**

I have implemented two different time series models. One is just depends
on the strain values as time $\varepsilon_t$.

$$ y_t = b \varepsilon_t + error_t $$

Here is the result when trying to predict the training samples
![](https://farm1.staticflickr.com/292/19512987286_7a2eeb97b0_o_d.png)

Here is the results when predicting a test sample.

![](https://farm1.staticflickr.com/556/19532383662_965d171970_o_d.png)


The other model is a first order auto-regressive model. The only
difference between the two models is there is now one term in the model
that takes into account the previous positon $y_{t-1}$

$$ y_t = a_1 y_{t-1} + b \varepsilon_t + error_t $$

Here is the results when predicting the training samples

![](https://farm1.staticflickr.com/366/19543367871_cfd64b7c3e_o_d.png)

Here is the results when predicting a test sample.

![](https://farm1.staticflickr.com/553/19351180718_12b5ce4095_o_d.png)

<!-- --horizontal -->
