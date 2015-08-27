---
layout: brough_slide
title:  "PyMKS"
subtitle: "Materials Knowledge Systems in Python"
date:   2015-04-09
author: David Brough
categories: presentation
tags: featured
---
<script type="text/template">
#**{{ page.title }}**
<br />
####**{{ page.subtitle}}**
###{{ page.author }}

--horizontal

###**ICME and MGI**
<br />

  Half the time at half the cost....

--horizontal

###**Troubles Multiscale Material Models**
<br />

  * Models for different length and time scales

  * Nonlinear field equations

--horizontal
###**Materials Knowledge Systems**
<br />

 * Data science approach for multi-scale materials science.

 * Previous "knowledge" to be applied to new microstructures.

 * Potential method for inverse material design.

--horizontal

### **Localization vs Homogenization**
<br />


 Localization &nbsp;  &nbsp; Homogenization

 $\Downarrow$  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; $\Uparrow$ &nbsp;  &nbsp;

 Top Down &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  Bottom Up &nbsp;  &nbsp;

--horizontal

### **Homogenization**


<br />

Quantify Structure $\rightarrow$ Reduce Dimension $\rightarrow$ Fit to Property

<br />

2-Point Statistics $\rightarrow$ PCA $\rightarrow$ Polynomial Regression

--vertical

![](https://farm6.staticflickr.com/5812/20745203380_3f98e0a7a8_b_d.jpg)

--vertical

### **Homogenization**
<br />

**2-Point Statistics** $\rightarrow$ PCA $\rightarrow$ Polynomial Regression

<br />

[Checker Board Example](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/checker_board.ipynb)

<br />

$$ f_r^{hh'} = \frac{1}{V} \sum_x m[x + r, t, h] m[x, t, h'] $$

--vertical

### **Homogenization**
<br />

2-Point Statistics $\rightarrow$ **PCA** $\rightarrow$ Polynomial Regression

<br />

[Sklearn PCA Example](http://scikit-learn.org/stable/auto_examples/decomposition/plot_pca_3d.html)

--vertical

### **Homogenization**
<br />

2-Point Statistics $\rightarrow$ PCA $\rightarrow$ **Polynomial Regression**

<br /> [Sklearn Polynomial Ridge Regression](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html#sklearn.linear_model.Ridge)

--horizontal

### **Localization**
<br />

Discretize Microstructure $\rightarrow$ Calibrate Kernels (Digital Filters)

<br />

Microstructure Function $\rightarrow$ Fit Influence Coefficients

--vertical

![](https://farm1.staticflickr.com/748/20745202890_fd4321a3ac_b_d.jpg)

--vertical

### **Localization**
<br />

Microstructure Function $\rightarrow$ Fit Influence Coefficients

[Elasticity Example](http://materialsinnovation.github.io/pymks/#technical-overview)

--horizontal

### **PyMKS Development Approach**
<br />

* Use abstractions from other libraries

* Use open source dependencies

* Have a permissive license

* Python has a large scientific code base

* Integration of docs and tests


--horizontal

### **PyMKS - API**
<br />

Homogenization and Localization Models

* model.fit(X, y)

  * X - Microstructure

  * y - Property

* model.predict(X)

  * X - Microstructure

--horizontal

### **PyMKS - 2-Point Statistics Example**
<br />
[Checkerboard Example](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/checker_board.ipynb)

--horizontal

### **Homogenization Example**
<br />

[Effective Stiffness](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/stress_homogenization_2D.ipynb)

--vertical
### **Sklearn - Dimensionality Reduction**
<br />

* PCA (Incremental, Randomized, Kernel, Sparse)

* Non-negative Matrix Factorization

* t-distributed Stochastic Neighbor Embedding

* Local Linear Embedding

* Spectral Embedding

* Isomap

* Linear Discriminant Analysis

--vertical
### **Sklearn - Regression Models**
<br />

* Linear Regression

* Lasso

* Logistic Regression

* Ridge Regression (Bayesian, Kernel)

* Support Vector Regression

* Isotonic Regression

* Bayesian ARD Regression

* Least Angle Regression

* Partial Least Squares Regression

--horizontal

### **Localization Examples**
<br />

[Structure-Property](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/elasticity_2D_Multiphase.ipynb)

[Structure-Processing](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/cahn_hilliard_Legendre.ipynb)

--horizontal

### **Future Development**
<br />

 * Generalize Spherical Harmonics

 * Microstructure Reconstruction

 * Additional Examples
