# 📘 Term Deposit Subscription Prediction

This project was completed as part of my learning journey with **Apziva**. The objective was to use machine learning techniques to identify clients who are most likely to subscribe to a term deposit product. By predicting high-likelihood subscribers, the project aims to support data-driven decision-making for targeted client outreach.

A **term deposit** is a fixed-term investment where a customer deposits a certain amount of money for a specified period and receives interest on it. Banks aim to maximize term deposit subscriptions, and this project addresses that need by building a predictive pipeline that assists in identifying potential subscribers efficiently.

---

## 🎯 Objective

To determine which clients are most likely to subscribe to a term deposit product using machine learning and exploratory data analysis, and to provide actionable recommendations for client call prioritization.

---

## ⚙️ Approach Summary

The project followed a structured data science workflow:

1. **Exploratory Data Analysis (EDA)**  
   - Conducted univariate and bivariate analysis to understand variable distributions and relationships.

2. **Dataset Splitting Strategy**  
   - Initially applied a validation-based split to test modeling strategies before using the final dataset.
   - Performed train-test split on the actual dataset for model training and evaluation.

3. **Model Selection**  
   - Several machine learning models were tested.
   - **Logistic Regression** was chosen due to its performance, simplicity, and alignment with the business goal.

4. **Handling Imbalanced Data**  
   - Compared **undersampling** and **oversampling** techniques.
   - **Oversampling** yielded better model performance and was used in the final model.

5. **Predicted Probability and Thresholding**  
   - Used predicted probabilities from the logistic regression model to rank clients.
   - Extracted **25th and 75th percentiles** to create segments of clients with different confidence levels.

6. **Target Selection**  
   - Segmented clients into two groups based on probability thresholds:
     - **Top 25% most likely** (75th percentile and above)
     - **Top 75%** (25th percentile and above)
   - Exported both target groups for client outreach prioritization.

7. **Clustering & Visualization**  
   - Applied **K-Means** and **Hierarchical Clustering** to identify natural groupings in the data.
   - Used **PCA**, **UMAP**, and **t-SNE** for dimensionality reduction and visualization.

8. **Data Filtering with DuckDB**  
   - Leveraged DuckDB to perform efficient SQL-like operations within the notebook.

---

## 📌 Key Findings

- Out of ~40,000 clients, the model identified **891 clients** as potential subscribers (True Positives + False Positives).
- **25th percentile segment** included **668 clients**, requiring only **147.77 hours** of call time.
- **75th percentile segment** included **223 clients**, needing just **73.58 hours** of call time.
- Contacting all 40,000 clients would require **2,831.38 hours**, demonstrating the efficiency gained through targeted outreach.

---

## 💡 Business Insights

- A small, high-confidence subset of clients drives the bulk of predicted positive outcomes.
- Focused targeting drastically reduces resource use while maintaining conversion potential.
- Probability thresholding provides a flexible framework for adjusting call strategy based on available resources.

---

## ✅ Recommendations

- **Primary Focus**: Contact the top 223 clients (≥75th percentile) for maximum efficiency and confidence.
- **Extended Option**: Include the top 668 clients (≥25th percentile) if more resources are available.
- Avoid full-scale outreach to all clients unless capacity is unlimited, as it is not resource-effective.
- Update the model periodically with real outcomes to improve accuracy over time.

---

## 📂 Project Structure

📦term-deposit-subscription-prediction
- 📄 term_deposit_analysis.ipynb
- 📄 clients_to_call_25th.csv
- 📄 clients_to_call_75th.csv
- 📄 README.md


---

## 🚀 Accomplishments

- Successfully built and evaluated a machine learning pipeline for classification.
- Implemented probability-based client segmentation.
- Delivered data-backed recommendations for business decision-making.
- Applied multiple clustering and visualization techniques for exploratory insights.
- Used DuckDB for in-notebook SQL querying and data manipulation.

---
