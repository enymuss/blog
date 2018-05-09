---
layout: post
title:  "Machine Learning Projects - 2"
date:   2018-04-03 16:00
categories: ml
---

---
### Luxsens ML Internship
<img src="/assets/MLProjects2/LuxsensHomescreen.png" alt="" style="width: 600px;"/>
Responsible for pushing forward ML & Data Analysis initiatives within the company.
Implemented image recognition algorithms in python to help cluster same products across crawled sites.
Improved crawling architecture by documenting the process and writing function to SQL database.

The program was added to the in-house admin panel and shown to investors.

---
### Comparison of Classifiers
<img src="/assets/MLProjects2/ComparisonOfClassifiers.png" alt="" style="width: 600px;"/>

Using the SpamBase Dataset, I compared the effectiveness of 4 classifier algorithms to classify spam.
The program run 10 cross-validation sets. Time shown is the total time taken to complete all 10 runs.

I was surprised to find that a vanilla Random Forest Tree increased the accuracy by 10% on the dataset, while decreasing the computation time. Built with Scikit-learn.

[Code on Github](https://github.com/enymuss/MLFUN/blob/master/ClassifierComparison.py)

---
### Shallow Classifier
<img src="/assets/MLProjects2/Cifar10ImageGrid.png" alt="" style="width: 600px;"/>

Created a Histogram of Oriented Gradients + SVM shallow classifier to serve as a benchmark on classifying the CIFAR-10 dataset, before using Inceptionv3.
Used HOG from scikit-image v0.14 which took into consideration the RGB data of the image, while the old HOG function allowed only grayscale images.

Using color images as training and testing improved the benchmark by 10%, from 32% to 42% accuracy on the test set.


[Code on Github](https://github.com/enymuss/TransferLearningCifar10)

---
### Transfer Learning
<img src="/assets/MLProjects2/PlotTransferValuesRainbow.png" alt="" style="width: 600px;"/>
<img src="/assets/MLProjects2/CNNCodes_PCA.png" alt="" style="width: 600px;"/>

Using the CIFAR-10 dataset, trained the Inception-v3 model network on 1/10th of the training dataset. Run the 1/10th through a standard SVM classifier with rbf kernel, got an accuracy of 82%. Tasked myself to improve the score to cross the 90% threshold.

First, run a grid search on the SVM classifier with rbf kernel, reaching 86.9% average accuracy on a 2-fold set with regularization parameter set to  2E+15 and gamma set to 2.00E-05. An improvement.

Next, I trained the Inception-v3 model on the full dataset, instead of the 1/10th.

Following that, I run a grid search using a linear svm. Using 1/10th of the dataset, again run 2-fold cross validation test to find the optimal regularization parameter.

First broad run got 0.871 (+/-0.007) average accuracy with C set to 0.002.

Next, I narrowed the range for C to smaller and smaller until I got the optimal C value, still comparing results on a 2-fold set. It converged to C = 0.002666 which got 0.873 (+/-0.004) accuracy.

After funding the optimal parameters, I trained the SVM classifier again on 1/5th and then on the full dataset and run the test.

Got a 90% Accuracy on the complete test set.

[Code on Github](https://github.com/enymuss/TransferLearningCifar10)

---
### Fashion CNN
<img src="/assets/MLProjects2/PredictedLables.png" alt="" style="width: 600px;"/>

Small project to learn PyTorch.
Run a CNN on FashionMNIST from Zalando dataset, to classify clothes.
Accuracy of the CNN on the 10'000 test image set: 85%.

[Code on Github](https://github.com/enymuss/MLFUN/blob/master/FashionMnistCNN.py)

---