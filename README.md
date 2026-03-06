# 🥗 Customer Churn Analysis

## Overview

This project analyzes customer churn behavior for a meal-kit subscription service using a synthetic dataset of 5,500 customers and 25 variables. The objective is to identify the major drivers of churn and develop predictive models that help businesses detect high-risk customers early.

The analysis combines exploratory data analysis and regression modeling to examine the relationships between customer demographics, engagement patterns, service quality, and financial behavior. Logistic regression was applied to estimate churn probability, while regression models were used to understand drivers of customer spending. The goal is to support data-driven retention strategies that protect long-term customer lifetime value.

---

## 💡 Key Insights

**Early lifecycle churn risk:**
Customer churn is heavily concentrated in the first 10 months of subscription, where churn rates approach 20–40%. After roughly 20 months, retention stabilizes significantly. This indicates that onboarding experience and early engagement are the most critical stages for retention.

**Operational reliability matters:**
Delivery issues and service dissatisfaction significantly increase churn risk. Even a small number of delivery problems can push churn probability above 20%, highlighting the importance of operational reliability in subscription businesses.

**Engagement signals predict churn:**
Friction points such as meal skips and reduced platform engagement elevate churn probability by 15%.

**Financial impact:**
The overall churn rate of 16.31% corresponds to an estimated $160,000 monthly revenue loss and over $3 million in potential lifetime value loss, emphasizing the financial importance of proactive retention strategies.

---

## 📊 Model Performance

### Multiple Linear Regression — Monthly Charges

| Metric | Baseline | Optimized |
|---|---|---|
| Adjusted R² | 0.8533 | **0.9829** |
| RMSE | 27.26 | **9.28** |

After applying train-test split and forward stepwise feature selection, RMSE increased marginally to 9.30, indicating strong model stability and minimal overfitting.

### Logistic Regression — Churn Prediction

| Configuration | Accuracy | Sensitivity |
|---|---|---|
| Baseline | 84.02% | ~10% |
| After SMOTE | 68.13% | 70.6% |
| SMOTE + threshold 0.4 | ~60% | **82%** |

> The initial model achieved 84% accuracy but detected only 10% of actual churners due to class imbalance. After applying SMOTE oversampling and lowering the classification threshold to 0.4, churn detection reached **82%**, enabling the model to generate weekly high-risk customer lists for proactive retention campaigns.

**Baseline AUC:** 0.735

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Excel | Data cleaning and preprocessing |
| R | Statistical modeling and predictive analysis |
| `tidyverse` | Data manipulation and visualization |
| `ROCR` | Model evaluation and ROC analysis |
| `themis` (SMOTE) | Handling class imbalance in churn prediction |
| Regression Models | Linear, multiple, and logistic regression |
