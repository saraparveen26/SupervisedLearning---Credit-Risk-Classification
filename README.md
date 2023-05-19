# Credit Risk Classification

## Overview of the Analysis

Following is a basic overview of the analysis performed for credit risk classification:

* The purpose of this activity is to train and evaluate machine learning models based on loan risk. The activity use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers and classify the credit risk predictions.

* The target financial information in the data is the loan status. The features in the financial data that are used to predict the loan status are loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks and total debt. 

* For the target values of `loan_status` there are two variables which I have tried to predict. The first set of variables have a value of '0' (value count of 75036) and these indicate that the loan is healthy. The second set of variables have a value of '1' (value count of 2500) and these mean that the loan has a high risk of defaulting.

* The machine learning process used to perform the analysis has following stages:
- Create label sets and feature Dataframe from the provided dataset.
- Split the data into training and testing datasets by using train_test_split.
- Create a logistice regression model and fit our original data into the model.
- Make predictions on testing data labels by using the testing feature data and the fitted model.
- Evaluate the model's performance by calculating accuracy scores, confusion matrix, and classification report.

* First method used in this case is the `LogisticRegression` model on the original fitted data. As the data was highly overweighted towards one of th etarget variables, so `RandomOverSample` was used to reduce the imbalances and LogisticRegression was then applied to the oversampled data.


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.