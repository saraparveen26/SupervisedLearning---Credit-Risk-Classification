# Credit Risk Classification

## Overview of the Analysis

Following is a basic overview of the analysis performed for credit risk classification:

* The purpose of this activity is to train and evaluate machine learning models based on loan risk. The activity use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers and classify the credit risk predictions.

* The target financial information in the data is the loan status. The features in the financial data that are used to predict the loan status are loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks and total debt. 

* For the target values of `loan_status` there are two variables which I have tried to predict. The first set of variables have a value of '0' (value count of 75036) and these indicate that the loan is healthy. The second set of variables have a value of '1' (value count of 2500) and these mean that the loan has a high risk of defaulting.

* The machine learning process used to perform the analysis has following stages:
 - Create label sets and feature Dataframe from the provided dataset.
 - Split the data into training and testing datasets by using train_test_split.
 - Create a logistic regression model and fit our original data into the model.
 - Make predictions on testing data labels by using the testing feature data and the fitted model.
 - Evaluate the model's performance by calculating accuracy scores, confusion matrix, and classification report.

* First method used in this case is the `LogisticRegression` model on the original fitted data. As the data was highly overweighted towards one of the target variables (healthy loans), so `RandomOverSampler` was used to reduce the imbalances and LogisticRegression was then applied to the oversampled data.


## Results

This section describes the accuracy and balanced accuracy scores, and the precision and recall scores of the two machine learning models used for the acitivity:

* Machine Learning Model 1 - **Logistic Regression**:

Following are the key results that can be drawn from the results computed by the Logistic Regression model that was performed on the original fitted data:

[Logistic Regression - Classification Report](Images/Image1.PNG)

  * This model does a good job in predicting both the healthy and the high-risk loans as can be inferred from the high accuracy score of 99.18% and balanced accuracy score of 95.20%. However, we have to take into consideration that the data is imbalanced as 96.77% of the target values (75036 out of 77536) are for the healthy loans. 

  * This model has a precision score of 100% for the healthy loans and 85% for the high-risk loans. This again can be attributed to the imbalance in the data. The precision scores imply that the healthy loans were classified correctly as positive 100% of the times. However, for the high-risk loans, the classification was correct only 85% of the times.

  * This model has a recall score of 99% for the healthy loans and 91% for the high-risk loans. The scores imply that for all the instances where the loans were actually healthy, 99% of the times they were classified correctly. However, for all the instances where the loans were actually high-risk, they were classified correctly 91% of the times.


* Machine Learning Model 2 - **RandomOverSampler**:

Following are the key results that can be drawn from the results computed by the Logistic Regression model that was performed on the data resampled through RandomOverSampler:

[RandomOverSampler - Classification Report](Images/Image2.PNG)

  * This model does a great job in predicting both the healthy and the high-risk loans as can be inferred from the high accuracy score of 99.38% and balanced accuracy score of 99.37%. 

  * This model has a precision score of 100% for the healthy loans and 84% for the high-risk loans. The precision scores imply that the healthy loans were classified correctly as positive 100% of the times. However, for the high-risk loans, the classification was correct only 84% of the times.

  * This model has a recall score of 99% for the healthy loans and 99% for the high-risk loans. The scores imply that for all the instances where the loans were actually healthy or when they were high-risk, 99% of the times they were classified correctly. 
  

## Summary

Based on the results described above, following are some key summary points:

* The random over sampled model seems to perform a better job as it has better accruacy score and balanced accuracy score compared to the model where logistic regression was performed on the oversampled data.

* The random over sampled method also does a better job in the correct prediction of loans as it has higher recall scores especially for the high-risk loans `1` and an equally good job for the healthy loans `0`. For any lending service company or credit grantor, the correct identification of a high-risk loan is much more important as it reduces the probabilty of defaultors by placing importance on correct analysis of their creditworthiness, thereby impacting the overall profitability of the company. The oversampled model does a way better job in correct classification of the high-risk loans(99%) when they were actually positive by catching the incorrect labelling of high-risk loans as healthy.

Taking into consideration the above key factors, my recommendation will be to use the `RandomOverSampler` method to resmaple the data in this scenario based on the overweighting towards healthy loans and then perform the Logistic Regression. This method gives better accuracy and recall scores which are crucial decision metrics for a lending service company.