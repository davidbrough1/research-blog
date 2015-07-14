---
layout: post
title:  "Transient MKS"
subtitle: "Multiscaling in Time"
author: David Brough
categories: post
---
{% include latex.html %}


###**Transient MKS**

The derivation in the paper shows that we should be able to pass only
an initial microstructure and convolve it will the influence coefficient
at a time $t$ of our choice and get the answer (provided the contrast
is small enough that the first order term is sufficient.)

$$ p[s, n] = \sum_{r=0}^{S-1} \sum_{l=0}^{L-1} \alpha[l, r, n] m[l, s - r, 0]  + ... $$

With that in mind I create 400 random initial microstructures (100 x 100), and solved
the Cahn-Hilliard equation for 500 time steps to get an initial microstructure
and final microstructure as inputs and outputs for the MKS calibration.

Here is a picture of one instance of calibration inputs and outputs.

![](https://farm1.staticflickr.com/549/19675942455_4f17577b46_z_d.jpg)

I then did the same cross validation procedure mentioned in the paper,
with the exception that now I am look at the R-squared value instead of
the MSE value.

![](https://farm1.staticflickr.com/487/19487947340_574e2bec3c_z_d.jpg)


I then calibrated two models, one for the Primitive basis one for the
Legendre Basis each with 2 local states.

Primitive

![](https://farm1.staticflickr.com/557/19680428321_e4400a6c82_z_d.jpg)

Legendre

![](https://farm1.staticflickr.com/320/19487905078_a445a7d754_z_d.jpg)

I create a new initial random microstructure and put into the Cahn-Hilliard
simulation for 500 time steps and the and the two MKS models for one long
time step.

Initial Microstructure

![](https://farm1.staticflickr.com/471/19053356484_ddd2376c35_o_d.png)

Results

![](https://farm1.staticflickr.com/467/19668831352_72d9946b81_z_d.jpg)

They each took the following amount of time to compute

 - Simulation - 1.22 sec
 - Primitive Basis - 2.34e-4 sec
 - Legendre Basis - 2.35e-4 sec

 The normlized MSE value for both the MKS models with respect to the
 simulation are

  - Primitive 3.04e-8
  - Legendre 3.05e-8

Plot of Differences

![](https://farm1.staticflickr.com/390/19649733116_0f293d9393_z_d.jpg)

I then increased the size of the domains from 100 x 100 to 300 x 300, and
used the same process to compute the structure evolution of the following
initial structure.

Initial Microstructure

![](https://farm1.staticflickr.com/321/19649733036_908b8a3384_o_d.png)

Results

![](https://farm1.staticflickr.com/276/19680428121_929faa94dc_b_d.jpg)

They each took the following amount of time to compute

 - Simulation - 10.8 sec
 - Primitive Basis - 1.40e-2 sec
 - Legendre Basis - 1.37e-2 sec

The normlized MSE value for both the MKS models with respect to the
 simulation are

  - Primitive 5.29e-9
  - Legendre 5.29e-9


Plot of Differences

  ![](https://farm1.staticflickr.com/275/19668831242_d09fcfd6f8_z_d.jpg)











