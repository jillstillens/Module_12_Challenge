# Module 12 Credit Risk Analysis Report

## Overview of the Analysis

This exercise allowed us to handle imbalanced data, first looking at just the original data as presented, then analyzing a second time using oversampling on the minority data in order to provide equal sample sizes.  The data itself was regarding credit applications, determining which loans are healthy and which are risky.

The data consisted of financial details, including loan amount, interest rate, borrower income, borrower debt-to-income ratio, number of accounts, number of deragotories (indicating late payments), total debt, and whether the loan is considered healthy (loan_status = 0) or risky (loan_status = 1).  The models were trained using the feature data, to predict whether the loan would be healthy or risky.

The first pass of the data used the data as-is, without accounting for the imbalance - the imbalancing being that in general loans are healthy, so overall there is a relatively low percentage of risky loans compared to healthy loans.  We read in the data, separated the features from the result (healthy or risky), and created training and testing data.  Next we created and trained a logical regression model, using the training data.  Lastly for this iteration we then tested the model with our testing data, and generated reporting statics based on the predictions compared to the actual results for the testing data.

The second pass of the data used the same inputs, but this time added a step by using RandomOverSampler to bring up the number of risky loans to match the number of healthy loans.  This was done to remove the possible skewness in the results due to the imbalance on inputs.  We then followed the same path as with the original data, creating and training a logical model using the oversampled data, and finally testing the model with the oversampled data and generating reporting statistics comparing the oversampled predictions to the actual results.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1: Using data as-is
  * Accuracy: .95204
  * Precision for healthy loans: 1.00
  * Precision for risky loans: .85
  * Recall for healthy loans: .99
  * Recall for risky loans: .91

* Machine Learning Model 2: Balancing the data using oversampling
  * Accuracy: .99367
  * Precision for healthy loans: 1.00
  * Precision for risky loans: .84
  * Recall for healthy loans: .99
  * Recall for risky loans: .99

## Summary

The accuracy rate indicates how often the model was correct with True Positives (TP) and True Negatives (TN).  At .95 Model 1 did quite well, athough Model 2 was much stronger with .99 accuracy.  The precision rate indicates how well the result was predicted.  Both models were 100% accurate in predicting healthy loans.  However, Model 1 did slightly better than Model 2 in precision for risky loans, at .85 compared to .84, respectively.  For Model 1 this means 85% of instances predicted as risky were actually risky, whereas for Model 2 84% of instances predicted as risky were actually risky.  Recall is a measure of actual positives compared to predicted positives.  Both models have a score of .99 for recall for healthy loans, meaning 99% of healthy loans were correctly identified.  But for risky loans, Model 1 had a recall of .91, while Model 2 had a much stronger recall of .99.

So overall, I would say Model 2, which used oversampling to account for the imbalance, is a stronger model based on the results indicated above.  Both are equally adept at predicting healthy loans, but Model 2 is also stronger at predicting risky loans.
