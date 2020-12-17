# Starbucks Capstone

# Overview
Starbucks, one of the world’s most popular coffee shops, frequently provides offers to its customers through its rewards app to drive more sales. These offers can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). This project is focused on tailoring the promotional offers for customers based on their responses to the previous offers and predict the response of a customer to an offer. Firstly, to best analyze the data thoroughly, Exploratory Data Analysis(EDA) is performed to find the data representations & characteristics. Secondly, machine learning models are built predict the customer’s response to an offer so that Starbucks can properly target who they send their offers to.

# Data Sets
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

# libraries used


import re

import math

import json

import pandas as pd

import numpy as np

import seaborn as sns

from matplotlib import pyplot as plt

from sklearn.ensemble import GradientBoostingClassifier, RandomForestClassifier

from sklearn.linear_model import LogisticRegression

from sklearn.preprocessing import MinMaxScaler

from sklearn.model_selection import train_test_split

from sklearn.metrics import accuracy_score, f1_score

from sklearn.metrics import fbeta_score, make_scorer

from sklearn.model_selection import GridSearchCV, RandomizedSearchCV

% matplotlib inline

# Motivation

This project to complete udacity Data Scientist Nanodegree capstone project I've chosen Starbucks data that mimics customer behavior on the Starbucks rewards mobile app, and build a model to predict the preferred offer by the clients


# The problem

that I chose to solve was to build a model that predicts whether a customer will respond to an offer. My strategy for solving this problem has two steps. First, I will combine the offer portfolio, customer profile, and transaction data. Each row of this combined dataset will describe an offer's attributes, customer demographic data, and whether the offer was successful. Second, I will assess the accuracy and F1-score of a naive model that assumes all offers were successful. This provides me with a baseline for evaluating the performance of models that I construct. Accuracy measures how well a model correctly predicts whether an offer is successful. However, if the percentage of successful or unsuccessful offers is very low, accuracy is not a good measure of model performance. For this situation, evaluating a models' precision and recall provides better insight into its performance. I chose the F1-score metric because it is "a weighted average of the precision and recall metrics".
