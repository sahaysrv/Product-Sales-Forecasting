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
 **Exploratory Data Analysis:** Gain insights into the distribution of features and relationships with sales.
**Feature Engineering:** Handle missing values, encode categorical variables, and create relevant features.
**Model Selection:** Implement and evaluate various models like Linear Regression, Random Forest, and XGBoost.
**Hyperparameter Tuning:** Tune models using techniques like Grid Search and Cross-Validation.
**Evaluation Metrics:** Use RMSE, MAE, and R² to evaluate the model's performance.

## Results

### Modeling Approach and Performance Improvement

The project includes two different modeling approaches. Initially, we observed a very high R² score using the training data, reaching **94%** with the XGBoost (XGB) model. However, when evaluating the model on the test set, we encountered a critical issue: the test data was missing one of the most important features—the `#Order` count column, which was present in the training set. Without this key feature, the model's performance on the test set significantly dropped, with the R² score falling to **73%**.

To address this, we implemented a **two-step modeling strategy** to improve prediction accuracy:

1. **Step 1**: We first trained a model to predict the missing `#Order` count.
2. **Step 2**: Using the predicted `#Order` values from Step 1, we then trained a second model to predict the final sales figures.

This two-step approach significantly improved the overall model performance. We were able to achieve a final R² score of **83%** on the test set—an improvement over the initial results when the `#Order` feature was missing.


