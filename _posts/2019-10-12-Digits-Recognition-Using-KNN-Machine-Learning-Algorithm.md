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
*Figure 1- Sample From Dataset*

Let's take a look at what the features represent after reshaping the 784 features set (pixels) into a square matrix of size 28x28 and plot each pixel color value. 
![sample-point]({{site.url}}/images/digits-recognition/sample-point.png)
*Figure 2- Features Representation For a Single Data Point*

And the barchart below represents the classes distribution for this dataset, this shows that we don't have to worry about class imbalance issues because the dataset is fairly balanced. 
![target-dist]({{site.url}}/images/digits-recognition/target-distribution.png)
*Figure 3- Barchart For The Target Distribution*

### 2. Learning Phase
#### A- Baseline 
The baseline model for this problem was built using K-Nearest Neighbors algorithm with all 784 features. The cross validation score for the baseline model is 0.97, which is great! However, if you are familiar with K-NN or have worked with it, you might be able to guess what's wrong with this model.. Exactly, time complexity. The big-O notation for K-NN is _dxn_, where d is the number of dimensions (features) and n is the number of instances. In my case, for several runs it took between 1h 10min to 4h 20min to build the model. Therefore, to enhance its performance I've worked on feature engineering the dataset to reduce its dimensions.

### B- Experiments
#### Feature Engineering 
To reduce the number of dimensions, I did the following: 
1. Take the features mean from every instance at each class. This will create a shape that is similar to all instances from that class which will act like templates for class labels (see Figure 4). 
2. Project the test samples through the templates and calculate how much pixels made it through.
3. The more pixels pass through a template, the more likely this test sample is identical to this digit shape. This rate is calculated for each instance with respect to each class label. 
This will result in generating 10 new features for each instance which represent the rate of similarity of this instance to all class labels. These 10 features are used to generate a new dataset and continue the training phase on this dataset instead of the original one (see Figure 5).

![number2-mask]({{site.url}}/images/digits-recognition/mask2.png)
*Figure 4- Template For Class Two*

![feature-engineered-dataset]({{site.url}}/images/digits-recognition/new-dataset.png)
*Figure 5- Dataset After Dimensionality Reduction*




