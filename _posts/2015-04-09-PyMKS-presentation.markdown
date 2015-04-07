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

[Materials Innovation Network](https://github.com/materialsinnovation)
![Materials Innovation](https://raw.githubusercontent.com/materialsinnovation/materialsinnovation.github.io/master/assets/matin_full_logo.png "Materials Innovation Network")

--vertical

Materials Innovation

 * [PyMKS](http://pymks.org)

 * [Project Pages](http://materialsinnovation.github.io/project-pages)

--horizontal
###**Materials Knowledge Systems**
<br />

 * Data science approach for multi-scale materials science.

 * Potential method for inverse material design.

--horizontal

## Localization vs Homogenization
<br />

 * Localization (Top Down)

 * Homogenization (Bottom Up)

--horizontal

## Homogenization
<br />

Quantify Structure $\rightarrow$ Reduce Dimension $\rightarrow$ Fit to Property
<br />
2-Point Statistics $\rightarrow$ PCA $\rightarrow$ Polynomial Regression

--vertical

## Homogenization
<br />

**2-Point Statistics** $\rightarrow$ PCA $\rightarrow$ Polynomial Regression

<br />

[Checker Board Example](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/checker_board.ipynb)

<br />

$$ f_r^{hh'} = \frac{1}{V} \sum_x m[x + r, t, h] m[x, t, h'] $$

--vertical

## Homogenization
<br />

2-Point Statistics $\rightarrow$ **PCA** $\rightarrow$ Polynomial Regression

<br />

[Sklearn PCA Example](http://scikit-learn.org/stable/auto_examples/decomposition/plot_pca_3d.html)

--vertical

## Homogenization
<br />

2-Point Statistics $\rightarrow$ PCA $\rightarrow$ **Polynomial Regression**

<br /> [Sklearn Polynomail Ridge Regression](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html#sklearn.linear_model.Ridge)

--horizontal

## Localization
<br />

Discretize Microstructure $\rightarrow$ Calibrate Kernel (Digital Filter)
<br />
Microstructure Function $\rightarrow$ Fit Influence Coefficients

--vertical

## Localization
<br />

Microstructure Function $\rightarrow$ Fit Influence Coefficients

[Elasticity Example](http://materialsinnovation.github.io/pymks/#technical-overview)

--horizontal

## PyMKS Development Approach
<br />

* Use abstractions from other libraries

* Use open source dependencies

* Have a permissive license (MIT)

* Python has a large scientific code base

* Integration of docs and tests


--horizontal

## PyMKS - API
<br />

Homogenization and Localization Models

* model.fit(X, y)

  * X - Microstructure

  * y - Property

* model.predict(X)

  * X - Microstructure

--horizontal


## PyMKS - Current Examples
<br />

[Examples](http://materialsinnovation.github.io/pymks/EXAMPLES.html)

--horizontal

## PyMKS - Future Examples
<br />
[Checkerboard Example](http://nbviewer.ipython.org/github/materialsinnovation/pymks/blob/develop/notebooks/checker_board.ipynb)

[Stess 2D Example](http://nbviewer.ipython.org/github/davidbrough1/pymks/blob/issue152-stress-example/notebooks/stress_homogenization_2D.ipynb)

