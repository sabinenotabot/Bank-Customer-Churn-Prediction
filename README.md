# Bank Customer Churn Prediction (Python) 

*Skills: Data Cleaning, Exploratory Analysis, Feature Engineering, Data Preprocessing, Model Tuning*

*Models Used: Naive Bayes, Logistic Regression, Decision Tree, Random Forest, KNN, SVC, XGB, Voting Classifier (ensemble model)*

## Project Overview 

### Objective 
The goal of this project is to better understand and predict customer churn (i.e. whether a costumer leaves or not) for a bank. I will identify and visualize factorst that contribute to customer churn and build a prediction model that will classify if a customer will churn or not. 

### Results and Insight


## Code and Resources Used 
**Python Version:** 3.7

**Packages:** pandas, numpy, sklearn, xgboost, matplotlib, seaborn

**Other Resources:**

[Towards AI article](https://towardsai.net/p/data-science/how-when-and-why-should-you-normalize-standardize-rescale-your-data-3f083def38ff): Article on how and when to apply normalization to data.

[KDnuggest article](https://www.kdnuggets.com/2019/01/fine-tune-machine-learning-models-forecasting.html): Article on model tuning techniques.

[Kaggle Notebook - Intro to Model Tuning](https://www.kaggle.com/willkoehrsen/intro-to-model-tuning-grid-and-random-search): More information on model tuning.

[Kaggle Notebook - Titanic Project Example](https://www.kaggle.com/kenjee/titanic-project-example): I roughly based the structure of this project on Ken Jee's attempt of the Titanic Kaggle competition. 

## The Dataset 

The Dataset is sourced from [Kaggle](https://www.kaggle.com/adammaus/predicting-churn-for-bank-customers) and contains information of characteristics of 10,000 customers of an unnamed bank and data on whether they left the bank or not. 

The following information on customers is included in the dataset: 

* **RowNumber** — Corresponds to the record (row) number. 
* **CustomerId** — Customer number used to track a customer across the bank.
* **Surname** — The surname of a customer. 
* **CreditScore** — The credit score of a customer 
* **Geography** — The location of a customer.
* **Gender** — The gender of a customer.
* **Age** — The age of a customer. 
* **Tenure** — The number of years that the customer has been a client of the bank. 
* **Balance** — The bank balance of a customer at the time the dataset was created.
* **NumOfProducts** — The number of products that a customer has purchased through the bank.
* **HasCrCard** — Indicates whether or not a customer has a credit card (0=No,1=Yes). 
* **IsActiveMember** — Indicates wether the customer is "active" (0=No,1=Yes).
* **EstimatedSalary** — The estimated salary of a customer. 
* **Exited** — Whether or not the customer left the bank (0=No,1=Yes).






