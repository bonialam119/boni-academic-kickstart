---
title: 'Assignment 01'
# subtitle: ''

authors:
- admin


# - Academic
categories:
# - Demo
date: "2020-01-01T10:00:00Z" 
# "2020-01-01T10:00:00Z"
lastmod: "`r format(Sys.time(), '%d %B %Y')`"
# "2020-01-01T10:00:00Z"
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# image:
#  placement: 2
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
#  focal_point: ""
#  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
Twitter has become an important communication channel in times of emergency. The ubiquitousness of smartphones enables people to announce an emergency they’re observing in real-time. Because of this, more agencies are interested in programatically monitoring Twitter (i.e. disaster relief organizations and news agencies). So in this blog we tried create a model to filter the disaster tweet among the thousands of tweets in real life.

## Software used for the study
- We used kaggle notebook as software tool for this study https://www.kaggle.com/kernels

## Data Collected
For the purpose of our study, we collected data from kaggle "Real or Not? NLP with Disaster Tweets" competition from the following link.https://www.kaggle.com/c/nlp-getting-started/data

## Tools used in NoteBook
For our study we imported different tools in Python. We imported numpy, pandas, tensorflow, standard scaler and others as shown below.

< img src="static/img/1.PNG" >

## Import Data
Kaggle uploaded three types of data for this study.
Train Data: Which includes text data or tweet, location and keyword with an id number. In target section it has two values: 1 for the tweet referring as disaster and 0 referring as non distaster tweet.
Test Data: Test data has the same attributes as train data sets. But target column is missing here. Which is the primary target for this study. 
Submission: A sample submission column of the results.
< img src="static/img/2.PNG" >

## Using Code for Data Cleaning and the model
For this purpose of the study we will use corpus stopwords, porter stemmer, count vectorize, train_test split. For model running we will be doing logistsic regression, so we imported logistic regression sklear.linear model.

## Data Cleaning
Using corpus we cleaned our data by removing hastags and other marks. We also made our data lower case for all. Follwing image showing an example of data before and after cleaning.


## Model Running
After cleaning the data we ran the model using Maximum 1000 words and fit the model with the training Data set. 
It shows model can predict 84% of training data set correctly.


## Predicting the test data set
Based on the fit model we predicted the test data set and submitted to kaggle for checking the accuracy. According to kaggle my model predicted 56 percent of test data set and I was ranked 3230 in the leaderboard. Link below shows my rank and score from kaggle.
https://www.kaggle.com/jobaidulalamboni/competitions


## The codes used 
Link below shows all the codes used in the study.
https://www.kaggle.com/jobaidulalamboni/trial-1

## References
https://www.kaggle.com/gunesevitan/nlp-with-disaster-tweets-eda-cleaning-and-bert
https://www.kaggle.com/mohamedabdullah/disaster-tweets-solution/notebook
https://www.kaggle.com/shahules/basic-eda-cleaning-and-glove
https://www.kaggle.com/holfyuen/basic-nlp-on-disaster-tweets/output
