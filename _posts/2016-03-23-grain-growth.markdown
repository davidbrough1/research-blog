---
layout: post
title:  "Grain Growth Questionable Results"
subtitle: "What I would like to propose"
author: David Brough
categories: post
---
{% include latex.html %}

# Grain Growth Questionable Results

This is an update on the grain growth project for the data challenge submission.

Recall we have four classes:

1. Banded
2. Rolling
3. Random
4. Uniform

While attempting to the build the process-structure linkage between the input (autocorrelation of pins to pins) and output (chord length distributions) we noticed that two classes were clustering well (banded and random), whereas the other two do not show any discernible trend the current available data (rolling and uniform).

## Recovering Chord Length Distribution from PCA
We can recover chord length distributions from our model using an inverse transform on the PCA data. This works for "normal" looking distributions as well as classes with "non-normal" chord length distributions.

**Original.**

![](https://farm2.staticflickr.com/1447/26013245615_3a9fdc7b60_o_d.png)

**Recover.**

![](https://farm2.staticflickr.com/1654/25712687770_f28a51751f_o_d.png)

## Scree Plots of PCA
The scree plots for both the input and output of our model capture much of the variance in a reasonable amount of PC values.

**Input.**

![](https://farm2.staticflickr.com/1481/25918360941_5a2d2e155a_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1579/25380523784_3060fddf44_o_d.png)

## PCA of All Samples
Here are the plots of PCA of all four classes color coordinated. 

**Input.**

![](https://farm2.staticflickr.com/1664/25712687660_e450c9c391_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1530/25384486213_2663536f8c_o_d.png)

Since the green and blue paths above are hard to see we can just plot them to zoom in and get a better spatial representation. Note: the green and orange have no relation to the green orange above, the two colors are simply to show class separation. 

**Input.**

![](https://farm2.staticflickr.com/1490/25712687350_2b518a2875_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1515/25987325076_d7b976a610_o_d.png)

# PCA of Only Banded and Random

We tried to build a model with these two PCA spaces but were having a hard time obtaining any reasonable results. We tried to throw out rolling and uniform classes and recomputing PCA to see if they were affecting the model.

Notice the more clear/distinct paths and wider separation in the new PCA basis when the rolling and uniform data is not present. 

**Input.**

![](https://farm2.staticflickr.com/1593/25892452272_c7bcda2125_o_d.png)
![](https://farm2.staticflickr.com/1716/25892452222_cca10a75da_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1537/25987325296_4fdd1eaebb_o_d.png)
![](https://farm2.staticflickr.com/1481/25380523294_d570511c58_o_d.png)

## Best Model
We obtained our best model from training on banded and random only in the master PCA model. We used standard 80%/20% test/train split.

```
Order of Polynomial: 3
Number of Components: 2
MSE: -5.18890555335e-05
R^2: 0.571955314915
```

Here is just one example of a chord length distribution in the test data and its corresponding predication from our model. We expect the curve to be smoother and retain a similar shape, but are unhappy with the peak magnitude discrepancy. 

**Original.**

![](https://farm2.staticflickr.com/1544/25892451732_8beb39aa2c_o_d.png)

**Prediction.**

![](https://farm2.staticflickr.com/1682/25892451662_ab70e7bfeb_o_d.png)

