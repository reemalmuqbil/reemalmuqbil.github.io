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
![header]({{ site.url }}/images/project-02/process.png)
*Figure 1- Development Phases*


The approach I have followed throughout developing this solution is illustrated in the Figure 1. It starts by a process for acquiring and building the dataset. The collected dataset is then cleaned using multiple techniques that is to be discussed in detail in the following sections. The explanatory data analysis phase starts before building the first model to explore the data, relationships, and its nature. After that, you can see a sign of iterative process, the first iteration of this stage represents the baseline model. The remaining iterations represents multiple trials of feature engineering, model building, and validation that stops once we optimize the model as much as we can. After choosing the best model, we run it into testing to measure its performance on unseen data.

#### Data acquisition 
 I started the process by gathering data from Malabar gold and diamonds website. I used web scraping tools including Selenium and BeatifulSoup to scrape the products features and prices. Like most of the online shopping websites, Malabar’s website doesn’t render all products applicable to the filtering criteria to minimize the page load time. It loads a small batch from the whole dataset of products, if the user decides that he/she is interested he/she will scroll down the page and wait a few seconds for the website to load the next batch of data. This implementation of data rendering made it impossible for me to scrape the data with BeatifulSoup. Therefore, I had to go for Selenium to simulate the human interaction of scrolling down the page, wait a few seconds for the page load time to finish, scroll down the page again and hit the “ Show more ” button if seen. This process was repeated until the whole data is loaded and all products are rendered in the HTML page (See GIF 1). The remaining web scraping functionalities which are accessing each product page and extracting its features were handled by BeautifulSoup perfectly. 

 ![demo]({{ site.url }}/images/project-02/load-demo.gif)
 *GIF 1- Load Page Demo*

#### Data cleaning
This stage has come to prepare the data for analysis and modeling with the following steps.
* Remove non-numerical characters from price values
 If you look at how the price values are stored in the dataset at the price_before_cleaning column, you can see that it contains the currency value and the string “(Approx)”. These strings shouldn’t be fed into our Machine Learning algorithm during the learning stage. Therefore, in this step, I have stored only the cost itself into the dataset. The result of this step is reflected on the price column in the Figure 2.

 ![demo]({{ site.url }}/images/project-02/price_col_transformation.png)
 *Figure 2- Price Column Cleaning*

