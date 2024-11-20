# Project 1: Customer Churn Prediction

## Table of Contents
1. [Overview](#overview)
2. [Steps Taken](#steps-taken)
3. [Results](#results)
4. [Suggestions for Improvement](#suggestions-for-improvement)

## Overview
This project predicts customer churn for a telecom company using machine learning algorithms. The goal is to identify customers likely to churn based on their demographics, services, and usage patterns.

### Objective:
- Analyze customer behavior to predict churn.
- Build a robust model using data preprocessing and feature engineering techniques.
  
## Steps Taken

### 1. Data Preprocessing:
- Merged four datasets (contract, personal, internet, and phone) based on `customerID`.
- Cleaned data by handling missing values (e.g., imputation, column removal).
- Created the target variable `Churn` based on the `EndDate` column.
  
### 2. Exploratory Data Analysis (EDA):
- Performed a detailed EDA to understand key features.
- Visualized distributions of numerical and categorical variables.
  
### 3. Model Development:
- Split the data into training and test sets, ensuring class balance.
- Trained the model using **XGBoost** with hyperparameter tuning.
  
### 4. Model Evaluation:
- Evaluated the model's performance using **ROC-AUC** and **Accuracy** metrics.
- Achieved an AUC-ROC score of 0.9063 and an accuracy of 85.61%.

## Results

The final model demonstrated a strong ability to predict churn, with an ROC-AUC score of 0.9063 and an accuracy of 85.61%. Below are the most important features used by the model:

### Feature Importance:
- **Type**: 60.38%
- **Service Length**: 8.77%
- **Multiple Lines**: 4.92%

## Suggestions for Improvement
- **Model Optimization**: Experiment with other models like LightGBM for potentially better performance.
- **Feature Engineering**: Investigate additional features like customer interactions, or behavior over time to improve predictions.
- **Business Outcome**: Focus on identifying high-risk customers early and offer retention strategies to reduce churn.
