# Naive-Bayes
In this exercise you will implement a Gaussian Naive Bayes classifier to predict the behavior of vehicles on a highway. In the image below you can see the behaviors you'll be looking for on a 3 lane highway (with lanes of 4 meter width). The dots represent the d (y axis) and s (x axis) coordinates of vehicles as they either…

change lanes left (shown in blue)
keep lane (shown in black)
or change lanes right (shown in red)

![GitHub Logo](https://github.com/GoldenFalcon1/Naive-Bayes/blob/master/pr6.png)

Your job is to write a classifier that can predict which of these three maneuvers a vehicle is engaged in given a single coordinate (sampled from the trajectories shown below).

Each coordinate contains 4 features:

s
d 
s-dot 
d-dot
 
You also know the lane width is 4 meters (this might be helpful in engineering additional features for your algorithm).

# Steps 

Implement the train(self, data, labels) method in the class GNB in classifier.cpp.

Training a Gaussian Naive Bayes classifier consists of computing and storing the mean and standard deviation from the data for each label/feature pair. For example, given the label "change lanes left” and the feature \dot{s} 
s
˙
 , it would be necessary to compute and store the mean and standard deviation of \dot{s} 
s
˙
  over all data points with the "change lanes left” label.

Additionally, it will be convenient in this step to compute and store the prior probability p(C_k)p(C k) 
for each label C_kCk	
 This can be done by keeping track of the number of times each label appears in the training data.

Implement the predict(self, observation) method in classifier.cpp.

Given a new data point, prediction requires two steps:

Compute the conditional probabilities for each feature/label combination. For a feature xx and label CC with mean \muμ and standard deviation \sigmaσ (computed in training), the conditional probability can be computed using the formula 
here: https://en.wikipedia.org/wiki/Naive_Bayes_classifier#Gaussian_naive_Bayes

