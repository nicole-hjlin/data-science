
# Predicting Online News Popularity with Regression and Classification Models
---
__This report is part of a group project from my Machine Learning course at the LSE. The goal is to play with and evaluate different machine learning models.__

## Data
We used the Online News Popularity Dataset from the [University of California Irvine Machine Learning Repos-
itory](https://archive.ics.uci.edu/ml/datasets/Online+News+Popularity) to predict the popularity of an online article--defined as the number of shares. The original authors of the dataset--Kelwin Fernandes, Pedro Vinagre and Paulo Cortez--achieved an accuracy rate of 67% using Random Forest Classifier. 

## Main results
Among our regression models, LASSO has the best predictive performance, with an MSE of 47,106,651.

![Table 1]('https://github.com/nicole-hjlin/data-science/blob/master/predicting-online-news-popularity/tables/classification%20performances.jpg')

Among our classication models, Extreme Gradient Boosting has the highest prediction accuracy of 68.25%.
With several data cleaning and parameter tuning techniques, our classification models beat the best performance
of models (67%) used by the original authors of the dataset.

![Table 2](/tables/classification performances.jpg)
