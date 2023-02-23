# phase_3_project


## Overview

   The goal of this project is to practice and reinforce the essential Machine Learning concepts learned in phase 3 of the Flatiron School curriculum. To achieve this, a GitHub Repository and a Jupyter Notebook will be created with code and notes, and a presentation will be given.

   The project will cover important topics such as cleaning and exploring data, creating features, selecting and evaluating models, and using machine learning algorithms such as linear regression, logistic regression, decision trees, and random forests.

   The project will conclude with a report that summarizes the key insights, challenges encountered, and lessons learned.

## Business Problem

   The objective of this project is to build a classifier for SyriaTel, a telecom company, to predict customer churn. The aim is to identify patterns in customer data that could indicate whether a customer is likely to leave the company or not.

   The problem is a binary classification, meaning we will be predicting whether a customer is likely to churn or not. By doing so, we hope to help SyriaTel focus on retaining valuable customers and reduce customer turnover.

## Data

   The SyriaTel Customer Churn dataset is a collection of data about SyriaTel's customers and their usage patterns, demographics, and account information. The dataset contains 3,333 rows, each representing a unique customer.

   The goal of this dataset is to use predictive modeling to identify the factors that contribute to customer churn in the telecom industry. To achieve this, the dataset includes a churn status variable that indicates whether a customer has left the company or not.

## Results

   Overall, the Random Forest Classifier with balanced class weight performed well in predicting customer churn, with high precision, recall, and f1-score for both churned and non-churned customers. These results suggest that this model can be used by telecom companies to identify and retain customers who are likely to churn.

              precision    recall  f1-score   support

           0       0.97      1.00      0.99       566
           1       1.00      0.84      0.91       101
           accuracy                           0.98       667
           macro avg       0.99      0.92      0.95       667
           weighted avg       0.98      0.98      0.98       667


  Based on the given confusion matrix, the model predicted positive churn correctly for 566 cases (true positives), did not predict positive churn when it wasn't the case for 85 cases (true negatives), but incorrectly predicted negative churn for 16 cases (false negatives), and did not make any incorrect positive churn predictions (false positives).
  
![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/Confusion%20matrix%20img.png)
