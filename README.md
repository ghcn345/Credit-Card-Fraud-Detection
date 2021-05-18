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

To protect the patients from honestly answering 'yes' or 'no' to this question related to cancer, a randomized procedure is initiated as follows:

1. We set up a threshold (m) first. If a random number < m, petients have to answer honestly.
2. If a random number > m, we set another random number to compare with the threshold again, i.e. yes for < m and no for > m.

The true ratio of the patients the cancer is p_true, and the observed ratio with noise is p_noise. Their mathematical relationship is 

```math
p_{noise} = m*p_{true} + 0.5*(1-m)
p_{true} = \frac{p_{noise}}{m} - \frac{0.5*(1-m)}{m}
```

The noise (m) can be added by taking numbers from Laplacian or Gaussian distribution.





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
