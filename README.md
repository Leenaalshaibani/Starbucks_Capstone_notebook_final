# Starbucks Capstone

# Overview
These days, if we are talking about the coffeeshops, for sure Starbuck will be in our mind, and all of the global companies are trying their best to apply many offers for their customers, in order to increase the number of sales and to get the benefits. these days, the offering and advertisement types and criteria get changed very fast with the technology and everyone now adays is competing with each other to do the best. In our project, we will create a model that will help Starbuck to predict the customers that will get the benefit from the offer. And also, it will help in getting an estimation number before applying the offer, and a correction later on to increase the benifets.

# Data Sets
The data is contained in three files:


portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)

profile.json - demographic data for each customer

transcript.json - records for transactions, offers received, offers viewed, and offers completed
Here is the schema and explanation of each variable in the files:


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


# The problem
build models that will be able to predict the customer’s response to an offer so that Starbucks can properly target who they send their offers to

# blog post 
https://lina-alshaibani.medium.com/starbucks-capstone-challenge-d1ef8fa50276

