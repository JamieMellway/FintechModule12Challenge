# Module 12 Report Template

## Overview of the Analysis

This analysis is looking at loans applications and whether or not the loan defaults.  This credit risk data will be imbalanced as there will be more non-defaulted loans (75036) than loans that defaulted (2500).  The data used is historical lending data from a peer-to-peer lending service.

We did two analyses of the data.  The first one was a logistic regression model that kept the data unbalanced.  The second analysis was also a logistic regression model but we used the RandomOverSampler module that brought the data to 56271.  Both used the 'lbfgs' solver.

## Results

* Machine Learning Model 1:
  * Balanced Accuracy Score: 0.9520479254722232
  * True Positive: 18663
  * False Positive: 56
  * False Negative: 102
  * True Negative: 563
  * Healthy Loan Precision: 1.00 
  * Healthy Loan Recall: 0.99
  * Healthy Loan F1 Score: 1.00
  * High-Risk Loan Precision: 0.85
  * High-Risk Loan Recall: 0.91
  * High-Risk Loan F1 Score: 0.88

* Machine Learning Model 2:
  * Balanced Accuracy Score: 0.9947308560359689
  * True Positive: 55964
  * False Positive: 286
  * False Negative: 307
  * True Negative: 55985
  * Healthy Loan Precision: 0.99 
  * Healthy Loan Recall: 0.99
  * Healthy Loan F1 Score: 0.99
  * High-Risk Loan Precision: 0.99
  * High-Risk Loan Recall: 0.99
  * High-Risk Loan F1 Score: 0.99

## Summary

The second model performed much better.  Oversampling the data fixed the issues with the low precision of the first model (0.99 versus 0.85).   Oversampling is recommended for such imbalanced data.

Giving out a high-risk loan is much worse than failing to grant a healthy loan.  This means that we are more concerned with False Positives than we are with False Negatives.  We want to minimize False Positives and so we want to maximize Precision. Precision here is more important than Recall.  Since the second model had a precision of 0.99 versus the first model's 0.85 precision, we recommend the second model.