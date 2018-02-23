---
layout: post
title:  "Machine Learning Projects"
date:   2017-06-03 16:00
categories: ml
---

---
### TensorFlow - Image Classification
<img src="/assets/MLProjects/1 - Tenserflow - Image Classification.png" alt="" style="width: 600px;"/>

An image classification program which, transferring learning from Inception v3 (trained for the ImageNet Challenge), classifies a given image as a daisy, sunflower, dandelion, tulip or rose. I used TensorFlow & Python for this project. It achieves and accuracy of ~90%. [Link to code.](https://github.com/enymuss/MLFUN/blob/master/label_image.py)

---
### Image compression
<img src="/assets/MLProjects/2 - compressed_image_comparison.png" alt="" style="width: 600px;"/>

The project used the k-means clustering algorithm. It scans an image and returns it using only the most popular 16 colors in the image. The other colors are assigned based on which of the other 16 colors they are closest to. The compressed image weighs 7 KB less, which means it was compressed by 64%.

---
### NLP - Text Classifier
<img src="/assets/MLProjects/3 - text_classification.png" alt="" style="width: 600px;"/>

The program tried to find the most popular customer questions asked by email. It took a whole mailbox, and filters only to get statements sent by customers. Then, it classifies each statement into Accept, Bye, Clarify, Continuer, Emotion, Emphasis, Greet, No Answer, Other, Reject, Statement, System, Wh-Question, Yes Answer andYes/No Question.

It uses a naive Bayes classifier, trained on the [NPS Chat Corpus](http://faculty.nps.edu/cmartell/NPSChat.htm). 

On the training set, it got a 63% classification accuracy. Seems a lot but the results were mostly unusable. [Link to code.](https://github.com/enymuss/eMail-Classifier)

---
### SVM - Spam Classifier
<img src="/assets/MLProjects/4 - SVM - Spam.png" alt="" style="width: 600px;"/>

This program used support vector machines (SVMs) to build a spam classifier. It achieved a 98% accuracy. 

---
### Neural Network - MINST Dataset
<img src="/assets/MLProjects/5 - NN - Minst Dataset.png" alt="" style="width: 600px;"/>

The classic ML project. Built a neural network from scratch which recognized handwritten digits form the MINST data set. It got 97.52% accuracy on the training set.

### Backpropagation for Neural Network
Expanding on the Neural Network project, added backward propagation from scratch to the neural network.

['Yes you should understand backprop' by Andrej Karpathy](https://medium.com/@karpathy/yes-you-should-understand-backprop-e2f06eab496b)

---
### Logistic Regression
<img src="/assets/MLProjects/6.1 - Linear Reg.png" alt="" style="width: 600px;"/>
<img src="/assets/MLProjects/6.2 - Cyclic Reg.png" alt="" style="width: 600px;"/>

A simple introduction project to get acquainted with fundamentals of machine learning through logistic regression.
The program computes costs for logistic regression (regularized and non-regularized), its gradients (regularized and non-regularized) and a prediction function. It achieves a 89% prediction accuracy for non-regularized and 83% for regularized functions.

---
### Anomaly Detection & Recommender Systems
<img src="/assets/MLProjects/7.1 - Anomaly.png" alt="" style="width: 600px;"/>
<img src="/assets/MLProjects/7.2 - Recommendation.png" alt="" style="width: 600px;"/>

In this project, I implemented an anomaly detection algorithm and applied it to detect failing servers on a network. Next, I used collaborative filtering to build a recommender system for movies.
The anomaly detection system estimates a Guassian fit, and highlights anomalies (servers which failed). It finds the optimal threshold value for an anomaly based on a crossed validation set based precision and recall (F1 score).
The movie recommender system computes recommended movies based on other users reviews. It creates a gradient for each movie and each user preferences based on their reviews.

