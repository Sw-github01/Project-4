# Sparkify Project

### Introduction

Customer churn, also known as customer attrition, in its most basic form, is when a customer chooses to stop using your products or services. With each customer who churns, there are usually early indicators that could have been uncovered with churn analysis.

### Project Motivation

This project is to use pyspark and apply machine learning techniques to build machine learning model and predict the customer churn event of Spotify data. It excercise load large datasets into Spark and manipulate them using Spark SQL and Spark Dataframes, as well as use the machine learning APIs within Spark ML to build and tune models.

### Project details

#### Pre-requisite

Python 3.7.6
PySpark Local 3.0.0
Jupyter Notebooks


#### Part I EDA

Details of Spotify data as below:

location: location of user, seems to append each new state (location, state)
gender: user gender (M/F/None)
page: what page the user is on during event (pages)
level: subscription level check uniqueness (free or paid)
auth: authenication (logged in/out)
length: time spent on page, max 50 mins on NextSong (if song paused??)
registration: unknown (registration unixtime)
ts: timestamp of event in ms (event unixtime)
userId: unique (userId val)
sessionId: unique sessionId per user?
itemInSession: lcounter for the number of items in a single session (item listened to in session)
firstName: users first name (not important, remove)
lastName: users lastname
artist: song artist
song: songname
userAgent: device/browser (not important for us, remove)
method: API PUT/GET http request (not important for us, remove)
status: http status

##### Part II Feature Engineering

This part is to derive new features based on the EDA process, and there are following features extracted/built:

root
 |-- userId: integer (nullable = true)
 |-- churn: integer (nullable = false)
 |-- gender: integer (nullable = false)
 |-- padi_level: integer (nullable = false)
 |-- thumbs_down_count: long (nullable = false)
 |-- thumbs_up_count: long (nullable = false)
 |-- page_vist_ct_hour: long (nullable = false)
 |-- avg_item_hour: double (nullable = true)
 |-- max_play_hour: long (nullable = false)
 |-- avg_length_hour: double (nullable = true)

#### Part III Model build and Evaluation
###### 3 machine learning techniques been excercised:
Logistic Regression
Random forest
Gradient Boosted Trees

###### mahicne learning pipeline
Along with excercising varied machine learning techniques, machine learning pipeline has been applied. which including data transformation and prediction through which data passes. The outcome of the pipeline is the trained model which can be used for making the predictions.

###### Machine learning model Evaluation and Result:
Results
Logistic regression: %
RFC: %
GBT: %

###### Detect Overfitting and solution
Cross validation: Use your initial training data to generate muliple mini train-test splits. Use these splits to tune your model. In standard k-fold cross-validation, we partition the data into k subsets, called folds. THen we iteratively trin the algorithm on k-1 folds while using the remaining fold as the test set.
Ensembles are machine learning methods for combining predictions from multiple separate models. There are a few different methods for ensembling, but the two most common are:
https://elitedatascience.com/overfitting-in-machine-learning

### Acknowledgements

Acknowledgements Open Source Acknowledgement. The Supported Packages are comprised of open source software, which is subject to the terms of the open source software license(s) accompanying or otherwise applicable to that open source software. You acknowledge that your own distribution or deployment of instances containing or linking to the Supported Packages or any other open source software may trigger open source license requirements for which you are responsible. Nothing in this Agreement limits your rights under or grants rights to you that supersede the terms of any applicable open source software license.

https://medium.com/@Sw001/spotify-customer-churn-prediction-using-pyspark-and-machine-learning-techniques-c95dcdc4084e
