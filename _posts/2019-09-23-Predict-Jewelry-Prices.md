---
layout: post
title: Predictin Jewelry Prices using Linear Regression
---

![header]({{ site.url }}/images/project-02/header.png)

### Introduction
This project’s idea hit me when I was thinking: Wouldn’t it be amazing to automate the role of jewelers or at least some of their functions? I mean, imagine having a robot or a system such that given a set of features of jewelry piece specifications, it can approximate its market value. I figured, why not build a Machine Learning model that can predict the prices of jewelry pieces given their characteristics. 


### Hypothesis 
It’s commonly known that jewelry prices are correlated with their weight, purity, and the characteristics of the stones if included. Therefore, I believe that a Linear regression model can perform well under these circumstances where the predicted value is continuous in nature and some of the features as well. 

### Methodology 
{% include image.html file={{ site.url }}/images/project-02/process.png description="Figure 1- Development Phases" %}

The approach I have followed throughout developing this solution is illustrated in the Figure 1. It starts by a process for acquiring and building the dataset. The collected dataset is then cleaned using multiple techniques that is to be discussed in detail in the following sections. The explanatory data analysis phase starts before building the first model to explore the data, relationships, and its nature. After that, you can see a sign of iterative process, the first iteration of this stage represents the baseline model. The remaining iterations represents multiple trials of feature engineering, model building, and validation that stops once we optimize the model as much as we can. After choosing the best model, we run it into testing to measure its performance on unseen data.