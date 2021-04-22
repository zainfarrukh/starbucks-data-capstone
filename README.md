# Starbucks Capstone Project for Data Scientist Nano Degree

## Business Case
Based on User data, Offer data and data related to user's interaction with offers, I will try to predict user behaviour. More specifically, I will try to predict how well users respond to the offers received by them.

## Project Description

First I will study the data using various visualization techniques and then I will use:

1) Supervised Machine Learning to try to predict the amount to be spent in Starbucks by the customer so that decision-makers can identify users on whom the offer works and can focus their efforts on those users.

2) Supervised Machine Learning to classify users based on the type of spenders ("high", "medium" or "low") and making offers based on that classification.

### Evaluation matrices for ML models
#### For Regression
As data would be most likely to be non-linear, I will use Support Vector Machines and appropriate evaluation matrix would be good-of-fit R2 "R-squared".  

#### For Classification
I will use either use Random Forrest Classifier or Support Vector Classifier and appropriate evaluation matrix would be accurcy score. I would also see precision, recall and F2 score to check for overfitting


## Data Introduction

This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

## Data Sets

The data is contained in three files:

portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)

profile.json - demographic data for each customer

transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

portfolio.json

id (string) - offer id

offer_type (string) - type of offer ie BOGO, discount, informational

difficulty (int) - minimum required spend to complete an offer

reward (int) - reward given for completing an offer

duration (int) - time for offer to be open, in days

channels (list of strings)

profile.json

age (int) - age of the customer

became_member_on (int) - date when customer created an app account

gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)

id (str) - customer id

income (float) - customer's income

transcript.json

event (str) - record description (ie transaction, offer received, offer viewed, etc.)

person (str) - customer id

time (int) - time in hours since start of test. The data begins at time t=0

value - (dict of strings) - either an offer id or transaction amount depending on the record

## Summary of the project
#### Cleaning the Data
I have cleaned the data to adjust for NaN values and outliers. Some of users' age was more than 110 which seems to be an anamoly and I have removed that for the analysis.
I have created three additional columns for data:
1) Average reward for each user from offers availed so far
2) Percentage completion of offers for each user (offers completed / offers received)
3) Whether user is a high spender or low (anyone who spends 5% or more of his income on starbucks will be classified as high spender)

#### Combining the Data
Data is located in 3 JSON files and I merged the data to be used in my analysis and creation of features.

#### Data Visualization
I used data visualization techniques to try to find insights in the data to use for in feature selection. Also I checked for any anomolies.

#### Extracting and Scaling the features
Relevant features where extracted and I used standard scaler to scale the features around their mean and standard deviation. Dummy variables were created to handle categorical data

#### Making Predictions
I used Support Vector Machines regression to predict total amount spent.

I used Random Forrest Classifier and Support Vector Classifier to predict whether user would be high spender or low spender.

#### Evaluating the Models
I used R2 to evaluate regression models. The results were not that great and models were only able to predict 22% of the total variance.

I used Accuracy score to compare between different models and checked precision and recall of final model to evaluate the performance. Major issue I faced was that classes were imbalanced and I had to resample the data in such a way that I had to undersample low and medium spenders so that each classifier is equally represented in the data to be fed into classifiers.

## Conclusion
ML regression model gives us key insights on likely purchase behaviour of the users as well. However, current features do not provide predictions which we can accurately rely on and we need to experiment with additional features to predict the actual amount of spend for each user.

Current data can be used to classify each user based on their spend behaviour and we can use that classification to target each user with respect to number of offers and type of offers to be offered.

We were able to get 75% accuracy using SVM classifier to predict whether user was a high spender or low spender. Although model has a good accuracy score but model had very poor results for high spenders (indeterminate F1-score). Model could not even predict a single high spender. It was because labels were very imbalanced.

One of the way we can counter this class imbalance is to undersample data from classes with higher frequencies. I have selected random samples from low and medium spenders so that total number of sample from each class is same and trained my models on those data and predicted the whole dataset from that trained model. Although my accuracy score reduced to 60.24%-61.26% but I got much better F1-scores in high spender class.

Based on on this information we can decide to which user we should offer the coupon offers. Coupon offers should be function of type of spender each user is i.e. users with high spend behaviour should get more coupon offers as they are more likely to make a purchase as well as relative difficulty of each coupon i.e. high spenders should be given coupon with greater difficulty.

## Next Steps
There is still much left to do to extract insights on user behaviour. We could do following additional activities to get more insights on the data:
1) Identify reason for anamolies in the data i.e. why people have more than 110 years age
2) Additional Features to improve accuracy of regression models
3) Get more samples so that we have sufficient set of high spenders
4) Test relationships between each type of offer and various classes of users.
5) Identify suitable clusterrings of users
6) Use Grid Search to check whether there is any better models with better hyper parameters
7) Use more granular search to find additional models which fit better on our data