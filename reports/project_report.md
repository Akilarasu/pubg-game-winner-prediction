# PUBG Game Winner Prediction

## Problem Statement

Player performance in PUBG depends on multiple gameplay factors such as combat efficiency, movement, and resource collection.

The goal of this project is to **predict the final placement percentage (`winPlacePerc`) of players in a PUBG match using gameplay statistics**.

## Challenges

* Large dataset with many features
* Different feature scales (distance vs kills)
* Complex nonlinear relationships between gameplay actions and match outcomes

## Approach

A **supervised machine learning regression approach** was used to model the relationship between player statistics and match placement.

### Steps

* Data preprocessing
* Exploratory Data Analysis (EDA)
* Feature scaling
* Model training
* Model evaluation

## Models Used

* Linear Regression
* XGBoost Regressor
* LightGBM Regressor

Tree-based boosting models were selected because they can **capture nonlinear relationships between gameplay features and match outcomes**.

## Model Evaluation

Evaluation metrics used:

**R² Score**
Measures how much variance in the target variable is explained by the model.

**Mean Absolute Error (MAE)**
Average absolute difference between predicted and actual values.

**Root Mean Squared Error (RMSE)**
Penalizes larger prediction errors more heavily.

## Model Performance

| Model             | Test R² | Test MAE | Test RMSE |
| ----------------- | ------- | -------- | --------- |
| Linear Regression | 0.839   | 0.089    | 0.123     |
| XGBoost           | 0.935   | 0.056    | 0.078     |
| LightGBM          | 0.933   | 0.057    | 0.079     |

XGBoost achieved the **best predictive performance**.

## Why Linear Regression Was Not Enough

Linear Regression assumes a **linear relationship between features and the target variable**.

However, gameplay statistics interact in complex ways such as:

* kills + movement
* damage + resource acquisition

Tree-based models like **XGBoost and LightGBM capture these nonlinear interactions more effectively**.

## Why Boosting Models Worked Better

Boosting algorithms improve prediction accuracy by **building models sequentially and correcting previous errors**.

Advantages:

* Handle nonlinear relationships
* Robust to feature interactions
* Perform well on structured tabular datasets

## Key Insights

* Player mobility strongly influences match performance
* Higher damage and kill counts increase winning probability
* Players who acquire more resources tend to achieve better placements

## Business Impact

This model can help gaming analysts and developers:

* Analyze player performance patterns
* Identify gameplay behaviors that lead to higher rankings
* Improve matchmaking and gameplay analytics
* Provide insights for competitive strategy development
