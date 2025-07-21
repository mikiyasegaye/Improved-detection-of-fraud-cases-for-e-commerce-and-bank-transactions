# Fraud Detection for E-commerce and Banking Transactions

## Project Overview

This project focuses on improving fraud detection for e-commerce transactions and bank credit transactions using advanced machine learning techniques. The goal is to create accurate and robust fraud detection models that handle the unique challenges of both types of transaction data.

## Business Context

- **Company**: Adey Innovations Inc. (Financial Technology Sector)
- **Focus**: E-commerce and banking solutions
- **Objective**: Improve fraud detection accuracy while balancing security and user experience

## Key Challenges

- **Class Imbalance**: Highly imbalanced datasets with far fewer fraudulent transactions
- **False Positives vs False Negatives**: Balancing security with user experience
- **Real-time Monitoring**: Efficient detection for quick response to threats

## Project Structure

```
├── data/
│   ├── raw/                 # Original datasets
│   ├── processed/           # Cleaned and processed data
│   └── interim/            # Intermediate data files
├── notebooks/
│   ├── 01_data_analysis/   # EDA and data exploration
│   ├── 02_feature_engineering/  # Feature creation and engineering
│   ├── 03_modeling/        # Model development and training
│   └── 04_evaluation/      # Model evaluation and comparison
├── src/
│   ├── data/               # Data processing scripts
│   ├── features/           # Feature engineering scripts
│   ├── models/             # Model training and prediction scripts
│   └── visualization/      # Plotting and visualization utilities
├── models/                 # Trained model files
├── reports/               # Generated reports and visualizations
├── config/                # Configuration files
└── requirements.txt        # Python dependencies
```

## Datasets

1. **Fraud_Data.csv**: E-commerce transaction data
2. **IpAddress_to_Country.csv**: IP address to country mapping
3. **creditcard.csv**: Bank transaction data

## Key Features

- Transaction frequency and velocity analysis
- Geolocation analysis using IP addresses
- Time-based feature engineering
- Advanced sampling techniques for imbalanced data
- Model explainability using SHAP

## Models

- **Logistic Regression**: Baseline interpretable model
- **Ensemble Model**: Random Forest or Gradient Boosting (XGBoost/LightGBM)

## Evaluation Metrics

- AUC-PR (Area Under Precision-Recall Curve)
- F1-Score
- Confusion Matrix
- Model explainability analysis

## Progress

### 1. Initial Data Exploration (`01_data_analysis/01_initial_data_exploration.ipynb`)

- Loaded and inspected all raw datasets: e-commerce transactions, IP-to-country mapping, and bank credit card transactions.
- Checked for missing values and duplicates, and performed initial data cleaning.
- Converted relevant columns to appropriate data types (e.g., datetime for timestamps).
- Performed univariate and bivariate exploratory data analysis (EDA), including class distribution, feature distributions, and basic correlations.
- Saved cleaned versions of all datasets to `data/processed/` for downstream tasks.

### 2. Geolocation Merging & Feature Engineering (`02_feature_engineering/01_geolocation_merging_and_feature_engineering.ipynb`)

- Merged e-commerce transaction data with IP-to-country mapping using numeric IP ranges.
- Filtered out transactions with IPs outside the available mapping range to ensure valid geolocation assignment.
- Engineered new features: time since signup, hour of day, day of week, transaction frequency, device/IP usage patterns, and country-based features.
- Encoded categorical variables for modeling.
- Saved the fully feature-engineered dataset to `data/processed/fraud_data_with_features.csv`.

These steps complete Task 1: Data Analysis and Preprocessing, and prepare the data for model building and evaluation.
