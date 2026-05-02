# Customer Churn Prediction using Neural Networks

## Project Overview

This project analyzes customer behavior in a telecommunications company to predict whether a customer is likely to churn. The goal is not only to build a predictive model but also to generate actionable business insights that can help reduce customer attrition.

---

## Objective

* Predict customer churn using a **feedforward neural network**
* Identify key factors influencing churn behavior
* Translate model insights into **business decisions**

---

## Dataset

* **Source:** Telco Customer Churn Dataset
* Contains customer demographics, service usage, billing details, and contract information
* Target variable: **Churn (Yes/No)**

---

## Data Preprocessing

* Removed irrelevant features (`customerID`)
* Converted `TotalCharges` to numeric and handled missing values
* Encoded categorical variables using one-hot encoding
* Scaled numerical features using StandardScaler

---

## Exploratory Data Analysis (EDA)

Key insights:

* 📌 **Contract Type:** Month-to-month customers show the highest churn
* 📌 **Tenure:** Customers with low tenure are more likely to churn
* 📌 **Monthly Charges:** Higher charges correlate with higher churn
* 📌 **Payment Method:** Electronic check users have higher churn
* 📌 **Demographics:** Customers without partners/dependents show higher churn

These insights guided feature selection for the model.

---

## Model: Feedforward Neural Network

* Architecture: Input → Dense(16) → Dense(8) → Output(1)
* Activation:

  * ReLU (hidden layers)
  * Sigmoid (output layer)
* Loss Function: Binary Cross-Entropy
* Optimizer: Adam

---

## Handling Class Imbalance

* Applied **class weights** to emphasize churn customers
* Performed **threshold tuning** to improve recall

---

## 📈 Model Evaluation

### Metrics Used:

* Accuracy
* Precision, Recall, F1-score
* Confusion Matrix
* ROC Curve (AUC = **0.85**)
* Precision-Recall Curve

---

### 🔍 Key Results

| Metric           | Value          |
| ---------------- | -------------- |
| Accuracy         | ~0.79          |
| Recall (Churn)   | up to **0.89** |
| F1 Score (Churn) | ~0.66          |

---

### Trade-off Insight

* Increasing recall improves detection of churn customers
* However, it increases false positives
* This trade-off is managed based on business priorities

---

## Business Insights & Decisions

### 1. Target High-Risk Customers

* Focus on:

  * Month-to-month contracts
  * High monthly charges
  * Electronic check users

📌 Action: Offer discounts or incentives

---

### 2. Improve Early Customer Experience

* High churn among low-tenure customers

📌 Action: Strengthen onboarding and early engagement

---

## ⚠️ Limitations

* Does not include external factors (competitors, customer satisfaction)
* Model interpretability is limited
* Dataset imbalance affects performance

---

## Key Takeaway

The model effectively identifies churn patterns and can support proactive retention strategies, though balancing recall and precision is critical for real-world deployment.




---
