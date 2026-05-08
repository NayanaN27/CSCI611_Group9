# Credit Card Fraud Detection Using Machine Learning and Neural Networks

## Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning and neural network models. Credit card fraud detection is an important real-world binary classification problem because fraudulent transactions are rare but can cause significant financial loss.

The goal of this project is to build and compare different classification models that can predict whether a transaction is legitimate or fraudulent. Since the dataset is highly imbalanced, the project focuses on appropriate evaluation metrics such as precision, recall, F1-score, ROC-AUC, and PR-AUC instead of relying only on accuracy.

A simple Streamlit web app is also included to demonstrate the final selected model.

---

## Dataset

The dataset used for this project is the Credit Card Fraud Detection dataset from Kaggle:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains anonymized credit card transaction features. Most features are PCA-transformed and labeled as `V1` through `V28`. The dataset also includes:

- `Time`: Seconds elapsed between each transaction and the first transaction
- `Amount`: Transaction amount
- `Class`: Target variable  
  - `0` = Legitimate transaction
  - `1` = Fraudulent transaction

The full dataset is not included in this repository because of file size. A small demo sample is included for testing the app.

---

## Project Goals

The main goals of this project are:

- Explore and preprocess the credit card fraud dataset
- Handle class imbalance
- Train baseline machine learning models
- Train and evaluate neural network models
- Add and compare an XGBoost model
- Evaluate models using fraud-detection-appropriate metrics
- Select the best-performing model
- Build a simple Streamlit app for demonstration

---

## Models Used

The following models were trained and compared:

1. Logistic Regression
2. Balanced Logistic Regression
3. Random Forest
4. Random Forest with threshold tuning
5. Neural Network
6. Improved Neural Network
7. XGBoost

---

## Final Model Selection

Based on the final comparison, the best model was:

**Random Forest with threshold = 0.3**

This model achieved the best balance between precision and recall based on F1-score. The threshold was adjusted from the default value to improve fraud detection performance.

---

## Model Comparison Summary

| Model | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Logistic | 0.7667 | 0.7041 | 0.7340 |
| Balanced Logistic | 0.1103 | 0.8980 | 0.1964 |
| Random Forest | 0.9506 | 0.7857 | 0.8603 |
| Random Forest (0.3) | 0.8660 | 0.8571 | 0.8615 |
| Neural Network | 0.6748 | 0.8469 | 0.7511 |
| Improved Neural Network | 0.5753 | 0.8571 | 0.6885 |
| XGBoost | 0.8778 | 0.8061 | 0.8404 |

The Random Forest model with threshold 0.3 had the highest F1-score, making it the final selected model for the app.

---

## Streamlit App

The app allows users to upload a CSV file containing transaction data and receive fraud predictions.

The app displays:

- Uploaded file summary
- Data preview
- Total number of transactions
- Predicted fraudulent transactions
- Predicted legitimate transactions
- Fraud prediction rate
- Actual vs predicted fraud count, if the `Class` column is included
- Prediction results preview
- Download option for full prediction results

---
