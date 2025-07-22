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
│   │   ├── Fraud_Data.csv
│   │   ├── IpAddress_to_Country.csv
│   │   └── creditcard.csv
│   └── processed/           # Cleaned and processed data
│       ├── Fraud_Data_clean.csv
│       ├── IpAddress_to_Country_clean.csv
│       ├── creditcard_clean.csv
│       └── fraud_data_with_features.csv
├── notebooks/
│   ├── 01_data_analysis/
│   │   └── 01_initial_data_exploration.ipynb
│   ├── 02_feature_engineering/
│   │   └── 01_geolocation_merging_and_feature_engineering.ipynb
│   ├── 03_modeling/
│   │   └── 01_model_building_and_training.ipynb
│   └── 04_evaluation/       # For future evaluation notebooks
├── src/                     # (Optional) Python scripts for data, features, models, visualization
├── models/                  # Trained model files
│   ├── best_fraud_model.pkl
│   └── best_credit_model.pkl
├── reports/                 # Generated reports and visualizations
├── config/                  # Configuration files
└── requirements.txt         # Python dependencies
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

### 3. Model Building and Training (`03_modeling/01_model_building_and_training.ipynb`)

- Prepared data for modeling, including feature selection and train-test split for both e-commerce and credit card datasets.
- Handled class imbalance in the training data using SMOTE (oversampling).
- Built and compared two models: Logistic Regression (baseline) and Random Forest (ensemble).
- Trained and evaluated both models using AUC-PR, F1-Score, and Confusion Matrix metrics.
- Compared model performance and selected Random Forest as the best model for both datasets, based on higher F1-Score and AUC-PR.
- Saved the best models for further explainability analysis.

## How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd <repo-directory>
   ```
2. **Set up a virtual environment (recommended):**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
5. **Run the notebooks in order:**
   - `notebooks/01_data_analysis/01_initial_data_exploration.ipynb`
   - `notebooks/02_feature_engineering/01_geolocation_merging_and_feature_engineering.ipynb`
   - `notebooks/03_modeling/01_model_building_and_training.ipynb`

## Tools and Libraries Used

- **Python 3.8+**
- **Jupyter Notebook**
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical operations
- **matplotlib, seaborn**: Data visualization
- **scikit-learn**: Machine learning models and preprocessing
- **imbalanced-learn**: Handling class imbalance (SMOTE, undersampling)
- **joblib**: Model saving/loading
- **tqdm**: Progress bars (optional)
- **xgboost, lightgbm**: (optional, for advanced modeling)
