# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of this anaylsis is to give an insight to businesses on the creditworthiness of borrowers. Using historical data machine learning models have been produced to give an insight into whether appplicants would pose a high risk or low risk for a loan. Overall it will allow the company to make a more informed choice about who is most cost effective clients to lend money. 

* Explain what financial information the data was on, and what you needed to predict.

The finanical data was historical lending activity from a peer-to-peer lending services company. We used the loan status to run our analysis.The factors condidered were:
-the size of the loan
-its interest rate
-the borrower's income
-the debt to income ratio
-the number of accounts the borrower held
-derogatory marks against the borrower
-the total debt
We predicted what type of risk status customers would pose were 0 means that the loan is healthy and a value of 1 means that the loan has a high risk of defaulting.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
The y variable (value_count) was representiing the loan_status.Initally we had   75036 (0) low risk and  2500 (1)high risk loans. 

* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

The dataset  was split into training and testing sets.The training set was used to build an initial logistic regression model (Logistic Regression Model 1) using the LogisticRegression module from scikit-learn. We fit a logistic regression model by using the training data (X_train and y_train).Then saved the predictions on the testing data labels. Finally by using the testing feature data (X_test) Logistic Regression Model 1 was then applied to the testing dataset. Following this the model was evaulated (see results below). All of which was done on the orginal data set. 

This intial model had an imbalance in the the data set it had 75,036 low-risk loan data points and 2,500 high-risk data points. To resample the training data and ensure that the labels had an equal number of data points, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. As a result it generated 56,277 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.The LogisticRegression classifier (Logistic Regression Model 2)and the resampled data was used to fit the model and make predictions (see results below). 



## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

The model shows a high degree of accuracy (99.2%) which is good. However, because the data set is inbalanced the accuracy is not  representative of the fact we are not able to catch all of the high-risk loan. From this model you are only able to catch 85% (precision) of the high risk loans and almost 100% precision of the healthy loans. In terms recall, it was able to give an 99% recall in predicting low-risk loans, but only 91% recall in predicting high-risk loans. Overall this not a bad model but more work would be needed before this goes into production.

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  
The model shows an increase in precision from 85 to 99% for high risk loans. Which when working with people and finances this is a good thing to have almost 100% accurracy and precision. Recall, accuracy and precision were giving an avarge of 99%.
However, due to the reshape the data was duplicated to balance it out so this added more data points.
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

Logistic Regression Model 2 had fewer false predictions of the testing data overall and would be the best model to use based on the high accuracy and recall of this model.However the data was duplucated to provide each data points. So this needs to be considered. I would find more historical data points an train this model further before deloying. You want to ensure you are not lending money to people who may not be able to pay it back so i think it is important to find the false predictions.
