# Crab Age Prediction Using Regression Models

## Overview
This project aims to predict the age of crabs based on physical attributes using regression-based machine learning models. The dataset includes features like weight, shucked weight, viscera weight, and shell weight, along with a categorical `Sex` feature. The goal is to build an accurate regression model for predicting age, applying data preprocessing, transformation, and multiple model comparisons.

## Objectives
- Preprocess raw crab measurement data
- Transform skewed features using square root transformations
- Encode categorical features
- Train and evaluate multiple regression models
- Generate final predictions 

## Dataset
- **Train file**: `train.csv`
- **Test file**: `test.csv`
- **Target**: `Age`
- **Features**:
  - Sex (M, F, I)
  - Weight
  - Shucked Weight
  - Viscera Weight
  - Shell Weight

## Key Steps

### 1. Data Preprocessing
- Encoded `Sex` column using integer mapping (`I`=0, `M`=1, `F`=2)
- Applied square root transformation to reduce skewness in:
  - Weight
  - Shucked Weight
  - Viscera Weight
  - Shell Weight
- Dropped original weight columns after transformation

### 2. Model Training
- Split the training data into train and validation sets
- Trained and evaluated the following models:
  - **Lasso Regression**
  - **Ridge Regression** with polynomial features (degree = 4)
  - **ElasticNet**
  - **XGBoost Regressor**

### 3. Evaluation
- Used **Mean Absolute Error (MAE)** as the primary evaluation metric
- Compared model performance and selected the best model for submission

### 4. Test Set Prediction
- Applied same preprocessing to `test.csv`
- Used the trained **Ridge Regression** model to generate final predictions
- Output saved as `results.csv` with `id` and `yeild` columns

## Technologies Used
- Python
- pandas, numpy
- scikit-learn
- matplotlib
- xgboost

## Results
- Ridge Regression with polynomial features achieved the best performance
- Final predictions prepared in the format suitable for competition submission
