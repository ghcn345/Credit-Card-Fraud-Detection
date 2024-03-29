<p>
<img src="images/cc.jpg" width="900" height="506">
</p>

# Credit Card Default Prediction

**Authors**: Ning Chen

## Overview
t is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

The [dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud) contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, ... V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.


## Exploratory Data Analysis (EDA)

Statistics for all of the variables
![groupby](/images/overall.jpg)


Relationship between exploratory variables and target variable
![overall](/images/class.jpg)



## Differential Privacy

To recognize fraud case in credit card transactions from honestly recording 'yes' (1) or 'no' (0) to this question, a randomized procedure is initiated as follows:

1. We set up a threshold (m) first. If a random number < m, credit card transactions have to be recorded correctly.
2. If a random number > m, we set another random number to compare with another threshold (n) again, i.e. 'yes' (1) for < n and 'no' (0) for > n.

The true ratio for the case of the fraudulent credit card transaction is p_true, and the observed case of the fraudulent credit card transaction is p_noise. Their mathematical relationship is 

![Figure](/images/eqn1.jpg)

when n = 0.5, the expressions can be simplified as

![Figure](/images/eqn2.jpg)

The noise (m, n) can be added by taking numbers from Laplacian, Gaussian or exponential distribution.



## Feature Engineering & Modeling Evaluation

![Figure](/images/roc_input.jpg)

![Figure](/images/roc_output.jpg)




## For More Information

Please review our full analysis in [our Jupyter Notebook](https://github.com/ghcn345/Credit-Card-Fraud-Detection/blob/master/FraudDetection.ipynb).

For any additional questions, please contact **Ning Chen—chen.ning345@gmail.com**.

## Repository Structure

Description of the structure of the repository and its contents:

```
├── README                              <- The top-level README for reviewers of this project
├── DefaultPrediction                   <- Narrative documentation of analysis in Jupyter notebook
├── creditcard                          <- sourced csv file from kaggle
└── images                              <- Both sourced externally and generated from code

```
