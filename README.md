# Customer Churn Analysis


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

# Confusion Matrix

  Based on the given confusion matrix, the model predicted positive churn correctly for 566 cases (true positives), did not predict positive churn when it wasn't the case for 85 cases (true negatives), but incorrectly predicted negative churn for 16 cases (false negatives), and did not make any incorrect positive churn predictions (false positives).
  
![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/Confusion%20matrix%20img.png)

# Feature Importance

  The feature importance was calculated and it showed that Total Charge is the strongest predictor of customer churn, followed by Customer Service Calls and International Plan. This suggests that customers are more sensitive to the cost of their telecommunications services and are more likely to leave when their bills are high. Additionally, customers who contact customer service frequently and those with international plans are also more likely to churn.

![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/feature%20importance.png)

# Total Charges

  The scatter plot shows that higher churn rates correspond with lower total charges, indicating a negative relationship between the two variables. It also highlights the minimum predicted total_charge value and the corresponding churn rate, which can help identify the point where customers are likely to cancel their service.
  
  The analysis suggests that customers are likely to consider leaving the company when their total charges reach around $58.45. Based on this insight, a potential strategy is to introduce a monthly plan that charges $58.00 to balance out losses from high spenders and increase satisfaction by offering more services.
  
![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/Total%20charge%20vs%20churn%20IMG.png)

# Customer Service Calls

  Customers who contact customer service frequently are more likely to churn. To address this issue, it is recommended to implement a training program for customer service representatives that emphasizes resolving customer problems within the first three calls. If the problem persists beyond three calls, it should be escalated to a more senior employee. This approach can help improve customer satisfaction and reduce the likelihood of churn.

![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/Churn%20vs%20customer%20service%20calls%20IMG.png)

# International Plan

  Only 9.7% of the customers in this dataset have an international plan. This is an interesting finding, as it suggests that the majority of the customers do not use the international plan.
  
 ![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/percentage%20of%20customers%20with%20international%20plan%20and%20churn.png)
 
  The analysis found that customers with an international plan were more likely to churn compared to those without the plan, with a churn rate of 42.4% compared to 11.5%, respectively. Given this finding, it is recommended that the company consider combining the international plan with the main plan to avoid customers feeling like they are paying extra for an additional service. By combining the plans, the company may be able to retain more customers who require international service, as they will not feel that they are paying extra for it.
  
![alt text](https://github.com/MichalOst3389/phase_3_project/blob/main/project%203%20images/churned%20customers%20by%20plan.png)

## Conclusions & Actionable Insights

  -Create a monthly plan and charge $58.00.
  
  -Implement training for customer service representatives to focus on resolving problems by the third call.
  
  -International plans are not very popular, they are still an important factor in customer churn. Combine international plans with the monthly plan to provide everything a customer needs into one plan.  
  
  
# Contact Information

  For any questions please contact MichalOst3389@gmail.com
 