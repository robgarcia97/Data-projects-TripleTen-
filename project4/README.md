# Predicting Taxi Demand with Machine Learning

## Project Description
Sweet Lift Taxi company has collected historical data on taxi orders at airports. To attract more drivers during peak hours, we need to predict the amount of taxi orders for the next hour. Build a model for such a prediction.

The RMSE metric on the test set should not be more than 48.

## Table of Contents
1. [Project Instructions](#project-instructions)
2. [Data Description](#data-description)
3. [Preparation](#preparation)
4. [Analysis](#analysis)
5. [Intermediate Conclusions](#intermediate-conclusions)
6. [Training](#training)
7. [Testing](#testing)
8. [Conclusion](#conclusion)

## Project Instructions
1. Download the data and resample it by one hour.
2. Analyze the data.
3. Train different models with different hyperparameters. The test sample should be 10% of the initial dataset.
4. Test the data using the test sample and provide a conclusion.

## Data Description
The data is stored in file `taxi.csv`. The number of orders is in the 'num_orders' column.

## Preparation
- Import necessary libraries and load the data.
- Convert the 'datetime' column to datetime format and set it as the index.
- Resample the data by one hour and create additional time-based features like 'hour' and 'day_of_week'.

## Analysis
- Perform exploratory data analysis (EDA) to understand the trends and seasonality of taxi orders.
- Visualize the number of taxi orders over time, the distribution of orders, and average orders per hour and day of the week.

## Intermediate Conclusions
- The data exhibits temporal patterns, with peak hours during the day and varying demand throughout the week.
- Time-based features, such as hour of the day and day of the week, may be valuable for modeling.
- The distribution of taxi orders is right-skewed, indicating most orders are lower with occasional high spikes.

## Training
- Create lag features (up to 12 hours) and rolling mean features to improve the prediction model.
- Split the data into training (90%) and testing (10%) sets.

## Testing
- Apply multiple machine learning models, including Linear Regression, Random Forest Regressor, and Gradient Boosting Regressor.
- Tune hyperparameters and use time series cross-validation to train and test the models.

## Conclusion
In this project, we successfully predicted taxi orders for Sweet Lift Taxi using historical data. We implemented multiple models and evaluated their performance based on RMSE. The Gradient Boosting Regressor model performed the best, meeting the RMSE requirement of ≤ 48, making it the optimal choice for predicting taxi demand.

This model can help Sweet Lift Taxi optimize driver availability during peak hours and improve overall operational efficiency.
