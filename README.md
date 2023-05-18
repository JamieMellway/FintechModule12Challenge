# Module 12 Report Template

## Overview of the Analysis

This analysis is looking at loans applications and whether or not the loan defaults.  This credit risk data will be imbalanced as there will be more non-defaulted loans (75036) than loans that defaulted (2500).  The data used is historical lending data from a peer-to-peer lending service.

We did two analyses of the data.  The first one was a logistic regression model that kept the data unbalanced.  The second analysis was also a logistic regression model but we used the RandomOverSampler module that brought the data to 56271.  Both used the 'lbfgs' solver.

## Results

* Machine Learning Model 1:
  * Balanced Accuracy Score: 0.9520479254722232
  * True Negative: 18663
  * False Negative: 56
  * False Positive: 102
  * True Positive: 563
  * Accuracy [(TP+TN)/(TP+TN+FP+FN)]: 0.99
  * Healthy Loan Precision [TN/(TN+FN)]: 1.00 
  * Healthy Loan Recall [TN/(TN+FP)]: 0.99
  * High-Risk Loan Precision [TP/(TP+FP)]: 0.85
  * High-Risk Loan Recall [TP/(TP+FN)]: 0.91

* Machine Learning Model 2:
  * Balanced Accuracy Score: 0.9947308560359689
  * True Negative: 55964
  * False Negative: 286
  * False Positive: 307
  * True Positive: 55985
  * Accuracy [(TP+TN)/(TP+TN+FP+FN)]: 0.99
  * Healthy Loan Precision [TN/(TN+FN)]: 0.99 
  * Healthy Loan Recall [TN/(TN+FP)]: 0.99
  * High-Risk Loan Precision [TP/(TP+FP)]: 0.99
  * High-Risk Loan Recall [TP/(TP+FN)]: 0.99

## Summary

The second model performed much better.  Oversampling the data fixed the issues with its high risk predictions.   Oversampling is recommended for such imbalanced data.

Giving out a high-risk loan is much worse than failing to grant a healthy loan.  This means that we are more concerned with False Negatives than we are with False Positives although both are important.  We want to minimize False Negatives and so we want to maximize Healthy Loan Precision and High-Risk Loan Recall.  Healthy Loan Precision values were similar with the two models (1.00 versus 0.99).  High-Risk Loan Recall values improved from the first model (0.91) to the second model (0.99).

It is also nice to see that the second model had a High-Risk Loan Precision of 0.99 versus the first model's 0.85 precision.

Between the two models, the second model is recommended.