# Fintech Customer Lifetime Value (CLV) and Churn Prediction

## Project Overview

This project analyzes the transaction behavior of 198,576 customers, re-framing a large retail dataset as a **Fintech** platform to define Customer Lifetime Value (CLV) and predict churn. The goal was to build an accurate predictive model to proactively identify high-risk customers based on their usage patterns.

## Key Findings & Business Insights

The primary finding shows that consistent engagement (frequency) is the most critical factor for customer retention.

### Churn Driver Importance

The Random Forest Classifier isolated three key features. Their relative importance scores demonstrate where retention effort should be focused:

| Feature | Feature Type | Relative Importance Score |
| :--- | :--- | :--- |
| **Total Transactions** | Frequency | **0.58 (58%)** |
| **Total Products** | Monetary Proxy | 0.36 (36%) |
| **Usage Diversity Count** | Breadth of Usage | 0.06 (6%) |

### Interpretation

* **Focus on Frequency:** Strategies designed to increase the number of transactions (e.g., promotional reminders) will yield a significantly higher return on investment than efforts to increase the variety of products purchased.
* **Retention Drop-Off:** Cohort analysis showed that retention drops steeply after the first transaction (**~62% retained at second order**). Customers who surpass 5 total transactions exhibit markedly lower future churn risk.

## Technical Summary

### Model Performance

The predictive model achieved an **ROC AUC of 0.67**. Crucially, the model recorded a **Recall score of 0.78** for the churn class (Class 1), indicating strong capability in identifying true positive churners.

### Project Pipeline & Tools

| Category | Tools & Libraries | Description |
| :--- | :--- | :--- |
| **Data Processing** | Python, Pandas, NumPy | Data cleaning, merging raw files, and creating a unified Transaction Log (3.2M+ rows). |
| **Feature Engineering** | Python (Custom Logic) | Created customer-level features: Recency, Total Transactions, Total Products, Cohort Group, and Usage Diversity Count (mapped Merchant Verticals). |
| **Modeling** | Scikit-learn | Built and tuned a Random Forest Classifier to predict the Recency-based `Churn_Flag`. |
| **Visualization** | Matplotlib, Seaborn | Used for cohort retention heatmaps and feature importance plots. |
