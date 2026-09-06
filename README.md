# AI-Driven Predictive Engine Diagnostics and Remaining Useful Life (RUL) Prediction

An AI-driven predictive maintenance project for turbofan engine health monitoring and Remaining Useful Life (RUL) prediction using the NASA C-MAPSS dataset.

The project focuses on predicting engine degradation and estimating the remaining useful life of aircraft turbofan engines. Multiple machine learning algorithms are evaluated and compared to identify effective approaches for predictive maintenance.

## Project Overview

Predictive maintenance helps identify potential equipment failures before they occur by monitoring degradation patterns and estimating the remaining useful life of a machine.

In this project, the NASA C-MAPSS turbofan engine dataset is used to develop and evaluate machine learning models for engine RUL prediction.

The project evaluates:

- Random Forest
- Gradient Boosting
- XGBoost

The models are evaluated across the four C-MAPSS operating conditions:

- FD001
- FD002
- FD003
- FD004

Performance is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Additional analysis includes feature importance and residual analysis to better understand model behavior and the factors influencing RUL prediction.

---

## Dataset

The project uses the **NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation)** turbofan engine dataset.

The dataset contains simulated run-to-failure sensor measurements from multiple turbofan engines operating under different conditions.

Four subsets are considered:

| Dataset | Description |
|---|---|
| FD001 | One operating condition and one fault mode |
| FD002 | Multiple operating conditions and one fault mode |
| FD003 | One operating condition and multiple fault modes |
| FD004 | Multiple operating conditions and multiple fault modes |

The target variable is the **Remaining Useful Life (RUL)** of the engine.

> The original NASA C-MAPSS dataset is not redistributed in this repository. Please obtain the dataset from the official NASA source and place it in the expected dataset directory.

---

## Objectives

The main objectives of this project are:

1. Load and preprocess the NASA C-MAPSS turbofan engine dataset.
2. Calculate Remaining Useful Life (RUL) for engine cycles.
3. Prepare sensor and operational features for machine learning.
4. Train multiple regression models.
5. Compare Random Forest, Gradient Boosting, and XGBoost.
6. Evaluate model performance using MAE, RMSE, and R².
7. Analyze feature importance.
8. Perform residual analysis.
9. Identify suitable machine learning approaches for predictive maintenance.

---

## Machine Learning Models

### 1. Random Forest

Random Forest is an ensemble learning method that combines multiple decision trees to perform regression.

It provides:

- Non-linear modeling capability
- Robustness to noisy features
- Feature importance analysis
- Good performance on complex relationships

### 2. Gradient Boosting

Gradient Boosting builds an ensemble of weak prediction models sequentially, with each model attempting to correct the errors of the previous models.

### 3. XGBoost

XGBoost is an optimized gradient boosting algorithm designed for efficient and accurate machine learning on structured/tabular datasets.

The three models are trained and evaluated under the same experimental framework to enable fair comparison.

---

## Evaluation Metrics

The models are evaluated using the following regression metrics.

### Mean Absolute Error (MAE)

Measures the average absolute difference between predicted and actual RUL values.

Lower MAE indicates better performance.

### Root Mean Squared Error (RMSE)

Measures the square root of the average squared prediction error.

Lower RMSE indicates better performance and gives greater importance to larger errors.

### R² Score

Measures how well the model explains the variance in the target variable.

Higher R² indicates better predictive performance.

---

## Analysis

In addition to model performance evaluation, the project includes:

### Feature Importance

Feature importance is analyzed to identify which sensor or operational variables contribute most to RUL prediction.

### Residual Analysis

Residuals are analyzed to identify:

- Prediction bias
- Error patterns
- Outliers
- Model weaknesses
- Differences between predicted and actual RUL

These analyses provide additional insight beyond the numerical evaluation metrics.

---

## Project Workflow

```text
NASA C-MAPSS Dataset
        |
        v
Data Loading
        |
        v
Data Preprocessing
        |
        v
RUL Calculation
        |
        v
Feature Preparation
        |
        v
Train / Test Data
        |
        +-------------------+
        |                   |
        v                   v
 Random Forest       Gradient Boosting
        |                   |
        +---------+---------+
                  |
                  v
               XGBoost
                  |
                  v
          Model Evaluation
                  |
        +---------+---------+
        |         |         |
        v         v         v
       MAE      RMSE       R²
        |
        v
Feature Importance
        |
        v
Residual Analysis
        |
        v
Predictive Maintenance Insights

## Note

The large Random Forest `.pkl` model file is not included in this repository due to its large file size. Other project files and model files are included. The Random Forest model can be regenerated by running the corresponding training notebook.
