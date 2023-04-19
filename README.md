# Credit Card Fraud Detection Model

### Background

This repository is part of the capstone project for the course Professional Certificate in Machine Learning and Artificial Intelligence from Imperial College of London. In this modelling work we are trying to solve the problem of detecting fraudulent credit card transactions. In the past few years, the massive usage of credit cards mostly for online shopping has caused a surge of frauds. So it is importan for financial institutions to create classification algorithms that can automatically detect fraudulent activities and block them.

We are using a dataset created by Worldline and the Machine Learning Group of Université Libre de Bruxelles, that is published in Kaggle (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?datasetId=310&sortBy=voteCount&searchQuery=decision+tree). This dataset contains credit card data from European customers, that took place on September 2013. All transactions occurred in a two days period. As expected for this type of problem the dataset is highly unbalanced and the positive class (frauds) accounts for 0.172% of all transaction entries. Thirty features, are provided in the source dataset:
* Inputs V1, V2 ... to V28 are numerical features and are the product of a principal component analysis. Due to confidentiality reasons we don't have information on the original data or their background.
* The "Amount" feature represents the amount transaction but we don't have information on the currency.
* The "Time" feature contains the seconds elapsed between each transaction and the first transaction in the dataset.
* The "Class" is the target variable, where value of 1 is the label for fraud and 0 is the opposite.


As part of this project we created a set of credit card fraud detection classifier, using different classification techniques, and compared their performace.The models can be found under the *notebooks/* directory. The modelling work can be split in to the following sections:  
1. Analysis of dataset: First we explored the source dataset and go through normal sanity checks. As the input features were already transformed, no further feature engineering was conducted.
2. We developed four classification algorithms using Logistic Regression, K-nearest Neighbors, Decision Trees and Random Forest. The original dataset was split into a training and test section using stratification to preserve the same distribution of fraudulent and non-fraudulent transactions in both datasets. Using hyperparameter search methods all four algorithms were tunned, using the train dataset. In order to increase the predictive ability of the classification algorithms we performed oversampling on the training dataset together with cross validation.
3. The best models identified from the previous step were compared using the test dataset. For this error analysis, the following classification metrics that are relevant for imbalanced problems were used:
    *  Area Under the Precision-Recall Curve metrics  
    *  Precision
    *  Recall
    * F1 score

A Datasheet and a Model Card can be found under the *docs/* folder.

## How to run the model

### 1. Set up environment
This repo uses poetry python packaging & dependency management tool.
* Step 1. Poetry Installation. If poetry is installed in your machine skip this step.\
    In a shell run:
        `$ curl -sSL https://install.python-poetry.org | python3 -`

    or for Mac users:
        `$ brew install poetry`

* Step 2. Establish a python virtual environment.\
In a shell run:
```
poetry shell
```
You can use the above command to every time you want to activate your environment.

* Step 3. Install the dependencies listed in the pyproject.toml file. Poetry will install all dependencies
including development dependencies.
```
poetry install
```

### 2. Download data
The data used for generating the classification algorithms, can be found here:  
(https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?datasetId=310&sortBy=voteCount&searchQuery=decision+tree)  

Before running the jupyter notebook found under the directory *notebooks/* you must download the data locally and place them inside a folder called *data* in the main directory. 

