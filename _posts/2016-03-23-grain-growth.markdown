---
layout: post
title:  "Grain Growth Questionable Results"
subtitle: "What I would like to propose"
author: David Brough
categories: post
---
{% include latex.html %}

# Grain Growth Questionable Results

Four classes:

1. Banded
2. Rolling
3. Random
4. Uniform

Banded and random cluster well, whereas rolling and uniform appear to mess up the model.

## Reconstructing Chord Length Distribution from PCA
Good reconstructions on multiple times of classes, even classes with non-normal chord length distributions.

**Original.**

![](https://farm2.staticflickr.com/1447/26013245615_3a9fdc7b60_o_d.png)

**Reconstruction.**

![](https://farm2.staticflickr.com/1654/25712687770_f28a51751f_o_d.png)

## Scree Plots of PCA

**Input.**

![](https://farm2.staticflickr.com/1481/25918360941_5a2d2e155a_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1579/25380523784_3060fddf44_o_d.png)

## PCA of All Samples

**Input.**

![](https://farm2.staticflickr.com/1664/25712687660_e450c9c391_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1530/25384486213_2663536f8c_o_d.png)

Plotting just a subset including banded and rolling classes to get a better idea of what is happening.

**Input.**

![](https://farm2.staticflickr.com/1490/25712687350_2b518a2875_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1515/25987325076_d7b976a610_o_d.png)

# PCA of Only Banded and Random

Throwing out rolling and uniform classes and recomputing PCA.

**Input.**

![](https://farm2.staticflickr.com/1593/25892452272_c7bcda2125_o_d.png)
![](https://farm2.staticflickr.com/1716/25892452222_cca10a75da_o_d.png)

**Output.**

![](https://farm2.staticflickr.com/1537/25987325296_4fdd1eaebb_o_d.png)
![](https://farm2.staticflickr.com/1481/25380523294_d570511c58_o_d.png)

## Best Model
From total PCA training on banded and random only. 80/20 test/train split.

```
Order of Polynomial: 3
Number of Components: 2
MSE: -5.18890555335e-05
R^2: 0.571955314915
```

**Original.**

![](https://farm2.staticflickr.com/1544/25892451732_8beb39aa2c_o_d.png)

**Prediction.**

![](https://farm2.staticflickr.com/1682/25892451662_ab70e7bfeb_o_d.png)

