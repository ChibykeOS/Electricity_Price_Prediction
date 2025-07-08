# Electricity_Price_Prediction
This repository contains a data science project focused on predicting electricity prices using a publicly available dataset. The project explores various steps of a typical machine learning workflow, from data loading and preprocessing to model training, evaluation, and advanced ensemble techniques like stacking.

## Project Overview

The goal of this project is to build a predictive model for electricity prices. Electricity price forecasting is a challenging task due to various influencing factors such as demand, supply (including renewable sources like wind and solar), weather conditions, and market dynamics.

## Dataset

The dataset used in this project is sourced from (https://raw.githubusercontent.com/amankharwal/Website-data/master/electricity.csv). It includes features like:
- Date and time information
- Holiday indicators
- Day of the week, week of the year, etc.
- Forecast and actual wind production
- System load
- Temperature and wind speed
- CO2 intensity
- Electricity price (the target variable)

## Project Steps

The project followed these key steps:

1.  **Data Loading and Exploration**: Loaded the data, examined data types, checked for missing values, and analyzed basic statistics.
2.  **Data Preprocessing**: Handled missing values (imputation), converted data types (to numeric and datetime), and addressed data inconsistencies.
3.  **Feature Engineering**: Created new time-based features from the datetime column to capture seasonality and temporal patterns.
4.  **Data Splitting**: Divided the dataset into training and testing sets.
5.  **Model Training and Evaluation (Initial)**: Trained an initial LightGBM Regressor model and evaluated its performance using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).
6.  **Performance Improvement - Outlier Analysis and Transformation**: Investigated outliers in the target variable through visualization and explored the effect of a log transformation on the target.
7.  **Performance Improvement - Hyperparameter Tuning**: Performed hyperparameter tuning on the LightGBM model using cross-validation to find optimal parameters.
8.  **Evaluation of Tuned Model**: Evaluated the tuned LightGBM model, which showed improved performance (MAE: 9.87, RMSE: 21.91).
9.  **Exploring Ensemble Methods - Stacking**: Began setting up a stacking ensemble framework to combine predictions from multiple diverse base models (Linear Regression, Ridge Regression, and tuned LightGBM) with a meta-model.

## Key Findings

- The initial LightGBM model provided a baseline prediction with notable errors, particularly for extreme values (indicated by the higher RMSE compared to MAE).
- While log transformation slightly improved MAE, it did not significantly reduce RMSE.
- Hyperparameter tuning on the LightGBM model significantly improved performance, reducing both MAE and RMSE.
- A stacking ensemble framework is being implemented to potentially further enhance predictive accuracy by leveraging the strengths of different model types.

## Future Work

- Complete the stacking ensemble implementation and evaluate its performance.
- Explore additional feature engineering opportunities (e.g., lagged features, rolling statistics).
- Experiment with different base models and meta-models within the stacking framework.
- Consider other advanced time series forecasting techniques.

## Technologies Used

- Python
- pandas
- numpy
- scikit-learn
- lightgbm
- matplotlib
- seaborn
