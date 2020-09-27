# Bank Customer Churn Prediction (Python) 

*Skills: Data Cleaning, Exploratory Analysis, Visualization, Pivot Tables, Feature Engineering, Data Preprocessing, Model Tuning*

*Models Used: Naive Bayes, Logistic Regression, Decision Tree, Random Forest, KNN, SVC, XGB, Voting Classifier (ensemble model)*

## Project Overview 

### Objective 
The goal of this project is to better understand and predict customer churn (i.e. whether a costumer leaves or not) for a bank. I will identify and visualize factorst that contribute to customer churn and build a prediction model that will classify if a customer will churn or not. 

### Results and Insight
[Fill in with results and insight]



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


## Data Cleaning 
After retrieving the data from Kaggle, I clean the data to improve the accuracy of my findings. Changes to the raw dataset include: 

* **Checking for null values:** It turns out that there are no null values included in the dataset
* **Removing irrelevant columns:** I remove the columns that include information on a customer's row number, customer ID and surname, as these characteristics are not relevant to predicting a customer's churn status

## Exploratory Analysis 

To gain an initial understanding of the data, I create several visualizations. For the numerical data, I create histograms to understand their distribution. For the categorical data, I create bar charts for the categorical data to understand the balance of classes. 

[Image]
[Image]


I also take a closer look at churn and the effect of different customer characteristics on it. In addition to a barchart, I create a pie chart of the churn ratio: 

[Image]

According to the data, around 20% of customers exited the bank. 

For the numerical data I create boxplots that visualize the impact of a customer characteristic on churn. For the categorical data I create additional barcharts that seperate classes into Exited/Retained to show how many members of each class exited or stayed with the bank. I also create pivot tables for both types of variables. Finally, I create a correlation matrix to visualize the correlation between the variables in our dataset. 



Based on the exploratory analysis, I conclude the following about the characteristics that influence customer churn: 
* Inactive members are more likely to leave the bank, as is expected. However, the data all shows that a good number of members is inactive. To reduce churn, the bank could focus on actively engaging with more members.
* Customers with a higher bank balance were more likely to exit, despite the fact that (after removing empty accounts) bank balance was close to normally distributed. This might indicate that the bank is not doing enough to serve customers who have a larger amount of money to deposit by, for example, offerin special products to heavy savers. 
* Surprisingly, older members were more likely to exit. The correlation matrix indicates that age is not strongly correlated with bank balance and is even positively (although weakly) with being an active member (which discourages churn). Therefore, the relationship between and age does not seem to be explained by these other factors. It might be worth investigating what the banks older members are lacking. 
* The proportion of female customers churning is greater than that of male customers. 
* Germany sees the greatest number of customers churn out of the three countries included in the dataset, despite having significantly fewer total customers than France. Potential explanations for this might include: different services being offered in Germany, customers needs being different in Germany, fiercer competition in the German market. 

## Feature Engineering 

I add two features to help improve the accuracy of the prediction model: 

* **BalanceSalaryRatio:** Expresses the ration of bank balance and estimated salary. This is a better indicator of which customers are heavy savers, as a higher salary often leads to a higher balance regardless of saving behaviour. This variable takes out the effect of salary on balance. 
* **TenureByAge:** Given that tenure is a 'function' of age, I introduce a variable aiming to standardize tenure over age.

## Data Preprocessing 

To prepare the data for modelling, I perform the following actions: 

1. For binary variables, I change to 0 values to -1 so that the model can register a negative relation when the characteristic does not apply
2. One Hot encode categorical variables
3. Apply Min Max Scaler to normalize the continuos variables that are not normally distributed 

## Model Building (Baseline Performance) 

To see how various different models perform with default parameters, I try the following models using 5 fold cross validation to get a baseline:

| Model | Baseline Performance | 
| --------------- | 
| Logistic Regression | 80.3% |
| Naive Bayes | 81.2% | 
| Decision Tree | 79.4% |
| K Nearest Neighbour | 81.5% |
| Random Forest | 85.9% |
| Support Vector Classifier | 82.9% |
| Xtreme Gradient Boosting | 85.1% |
