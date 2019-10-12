---
layout: post
title: Digits Recognition Using KNN Machine Learning Algorithm
---

![header]({{ site.url}}/images/digits-recognition/digits.png)

## Introduction 

## Methodology 

### 1. Dataset acquisition and EDA 
This article is going to use a popular open source dataset called [MNIST original](https://www.kaggle.com/avnishnish/mnist-original). It is a dataset consisting of 70,000 images of handwritten digits. The features are the pixels of the image which are 784 pixels and a class label which is the digit value.
This is what the dataset looks like: 
![dataset-sample]({{site.url}}/images/digits-recognition/dataset-sample.png)

Let's take a look at what the features represent after reshaping the 784 features set (pixels) into a square matrix of size 28x28 and plot each pixel color value. 
![sample-point]({{site.url}}/images/digits-recognition/sample-point.png)

And the barchart below represents the classes distribution for this dataset, this shows that we don't have to worry about class imbalance issues because the dataset is fairly balanced. 
![target-dist]({{site.url}}/images/digits-recognition/target-distribution.png)

