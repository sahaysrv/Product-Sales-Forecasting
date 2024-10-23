# Sales Prediction using Machine Learning

## Project Overview

This project aims to build a machine learning model to predict sales based on historical data from multiple stores across various regions and store types. The dataset contains information about store characteristics, holiday periods, and the number of orders, which will be leveraged to create predictive models that can forecast future sales.

## Dataset Information

- **File Name**: `TRAIN.csv`
- **Total Records**: 188,340
- **Total Features**: 10

The features in the dataset are:

| Column          | Description                                                      |
|-----------------|------------------------------------------------------------------|
| **ID**          | Transaction ID, unique for each record                           |
| **Store_id**    | Store identification number                                      |
| **Store_Type**  | Type of store (S1, S2, S3, S4)                                   |
| **Location_Type**| Type of location (L1, L2, L3)                                   |
| **Region_Code** | Region code indicating where the store is located                |
| **Date**        | Transaction date                                                 |
| **Holiday**     | Binary variable (1 = Holiday, 0 = Non-Holiday)                   |
| **Discount**    | Whether a discount was applied (Yes/No)                          |
| **#Order**      | Number of orders placed on the specific date                     |
| **Sales**       | Sales amount in the local currency                               |

## Objective

The main goal of the project is to develop a machine learning model that predicts the **Sales** based on the other variables provided in the dataset.


## Key Steps
### Exploratory Data Analysis: Gain insights into the distribution of features and relationships with sales.
### Feature Engineering: Handle missing values, encode categorical variables, and create relevant features.
### Model Selection: Implement and evaluate various models like Linear Regression, Random Forest, and XGBoost.
### Hyperparameter Tuning: Tune models using techniques like Grid Search and Cross-Validation.
### Evaluation Metrics: Use RMSE, MAE, and R² to evaluate the model's performance.

## Results
The project has two different Model Files, in the first scenario we had a very high r2_score using the training data, but we noticed that the test set had one of the important features missing that was the '#order' count column. In our training split, we received very high r2_score of 94% with XGB but after removing the '#order' column, like the test set, the r2_score dropped to 73%.
Therefore, to improve model performance in predicting sales numbers we have done a 2-step projection. In the first step we have predicted the '#order' column and in the second step we have predicted 'sales'.
It was worth noting that this improved our model performance and we could achieve our final r2_score at 83%.

