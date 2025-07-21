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
