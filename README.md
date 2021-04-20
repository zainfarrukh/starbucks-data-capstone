# Starbucks Capstone Project for Data Scientist Nano Degree

## Business Case
Based on User data, Offer data and data related to user's interaction with offers, I will try to predict user behaviour. More specifically, I will try to predict how will users respond to the offers received by them.

## Project Description

Supervised Machine Learning to predict amount to be spent in Starbucks by the customer, their average reward on offers and percentage of offers completed by each user so that decision makers can identify users on whom the offer works and can focus their efforts on those users.

Also using Supervised Machine Learning to classify users based on type of spenders ("high", "medium" or "low") and making offers based on that classification

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
I have cleaned the data to adjust for NaN values and outliers.

#### Data Visualization
I will use data visualization techniques to try to find patterns in the data to use for in feature selection.

#### Combining the Data
Data is located in 3 JSON files and I will merge the data to be used in my analysis and creation of features.

#### Extracting and Scaling the features

#### Making Predictions
#### Evaluating the Models
