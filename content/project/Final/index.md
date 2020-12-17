---
title: Final Project
tags:
date: "2020-10-26T00:00:00Z"
permalink: /content/project/assignment-1/index

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption:
  focal_point: Smart

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---
Introduction: 

Text analysis is one of the great achievements of Artificial Intelligence and in last few years it has become an
important and most popular from of data mining. Text data analysis has become an important part in every
analytical fields from social media analytics to fraud detection to spam identification even to the analysing traffic
congestion to disaster analysis. In this project we will try to understand how different data mining techniques can
help to classify text of a big set of data.

Board Game Geek Rating Predictor: 

Board Game Geek is an online platform that discusses content, idea and thoughts of different board games
around the world. It has more than two million registered users and one of the largest hub of this kind. BGG
includes reviews, ratings, images, play-aids, translations, and session reports from board game enthusiast
around the world. Based on all those discussion we will try to predict the rating of the games based on thier
reviews and thoughts. We have collected the data of 15 millions reviews from
https://www.kaggle.com/jvanelteren/boardgamegeek-reviews
(https://www.kaggle.com/jvanelteren/boardgamegeek-reviews). We will try different data minining techniques and
will try to find out which techniques will provide the best

Data Description and Pre-Processing:

Data consist of two sets of data set. One data set is full of reviews from different users and other data set consists of detail information about different games. 
One of the important steps of any text data mining is text pre-processing. In our study we will do some text pre-processing processes described below-

1.Tokenization: Tokenization is a step which splits longer strings of text into smaller pieces, or tokens. Larger chunks of text can be tokenized into sentences, sentences can be tokenized into words, etc. Further processing is generally performed after a piece of text has been appropriately tokenized. Tokenization is also referred to as text segmentation or lexical analysis. Sometimes segmentation is used to refer to the breakdown of a large chunk of text into pieces larger than words (e.g. paragraphs or sentences), while tokenization is reserved for the breakdown process which results exclusively in words.

2. Normalization: Next step of the text processing is we need to normalize the data. In this study we will do two types of normalization- converting all the words into lower case. Next we will remove all the stops words in the data. Stop words are those words which are filtered out before further processing of text, since these words contribute little to overall meaning, given that they are generally the most common words in a language. For instance, "the," "and," and "a," while all required words in a particular passage, don't generally contribute greatly to one's understanding of content. 

3. Noise removal: Noise Removal is removing the unwanted characters and symbols from the sentence that does not include any value to context while text processing. There are different packages and library's that can be used to remove this noises. 


Applying Data Mining Technique for Text Classification

Naive Bayes Classifier:

Naive Bayes classifiers are linear classifiers that are known for being simple yet very efficient. The probabilistic model of naive Bayes classifiers is based on Bayes’ theorem, and the adjective naive comes from the assumption that the features in a dataset are mutually independent. In practice, the independence assumption is often violated, but naive Bayes classifiers still tend to perform very well under this unrealistic assumption. Especially for small sample sizes, naive Bayes classifiers can outperform the more powerful alternatives.

Being relatively robust, easy to implement, fast, and accurate, naive Bayes classifiers are used in many different fields. Some examples include the diagnosis of diseases and making decisions about treatment processes , the classification of RNA sequences in taxonomic studies , and spam filtering in e-mail clients .
However, strong violations of the independence assumptions and non-linear classification problems can lead to very poor performances of naive Bayes classifiers.
We have to keep in mind that the type of data and the type problem to be solved dictate which classification model we want to choose. In practice, it is always recommended to compare different classification models on the particular dataset and consider the prediction performances as well as computational efficiency.

The advantages of support vector machines are:

Effective in high dimensional spaces.

Still effective in cases where number of dimensions is greater than the number of samples.

Uses a subset of training points in the decision function (called support vectors), so it is also memory efficient.

Versatile: different Kernel functions can be specified for the decision function. Common kernels are provided, but it is also possible to specify custom kernels.

The disadvantages of support vector machines include:

If the number of features is much greater than the number of samples, avoid over-fitting in choosing Kernel functions and regularization term is crucial.

SVMs do not directly provide probability estimates, these are calculated using an expensive five-fold cross-validation.

[[pdf link]](/img/f.pdf)
[[html link]](/img/ff.html)
[[notebook link]](/img/fm.ipynb)
