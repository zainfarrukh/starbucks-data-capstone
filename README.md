# Starbucks Capstone Project for Data Scientist Nano Degree
## Introduction

This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

## Project Description

Supervised Machine Learning to predict amount to be spent in Starbucks by the customer, their average reward on offers and percentage of offers completed by each user so that decision makers can identify users on whom the offer works and can focus their efforts on those users

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
#### Data Visualization
#### Combining the Data
#### Extracting and Scaling the features
#### Making Predictions
#### Evaluating the Model
