---
layout: post
title:  "Predicting Phase Field Simulation Parameter"
subtitle: "Cahn-Hilliard Simulatoin"
author: David Brough
categories: post
---
{% include latex.html %}

The Cahn-Hilliard equation only has one $\gamma$ that can be varied
which controls in the interface thickness during the phase separation.

$ \dot{\phi} = \nabla^2 \left( \phi^3 - \phi \right) - \gamma \nabla^4 \phi $

I create 500 microstructures (51 x 51) that each used a random value
of $\gamma$ that was generated from a uniform distribution on the
interval 0 to 0.04 as a calibration dataset. Below are a few examples
of the microstructures.

![](https://farm2.staticflickr.com/1491/25113921275_8a2db6e8e5_o_d.png)

I also created 25 additional microstructures with random instance of
$\gamma$ from the same distribution.

I then used create a linkage using a second order polynomial regression
with 4 principal components.

![](https://farm2.staticflickr.com/1689/24818294650_5cdf62bb3f_o_d.png)
