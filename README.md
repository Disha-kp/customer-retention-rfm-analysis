Customer Retention & RFM Segmentation Analysis

BUSINESS PROBLEM: A retail/SAAS business wants to identify who its most valuable customers are, detect drop-off(churn) early, and undertsnad how customer retention evolves ovr time 

This is an end-to-end data analytics project evaluating customer purchase patterns, cohort retention dynamics, and strategic customer segmentation using Python, DuckDB (SQL), and Plotly.

Project Overview
This project analyzes online retail transaction data to identify retention drop-off points and build strategic RFM (Recency, Frequency, Monetary) segments. 

Key Business Questions Addressed:
1. What is the month-over-month customer retention drop-off rate?
2. How is total revenue distributed across customer loyalty tiers?
3. Which high-value customers are currently **At Risk** of churn and require targeted win-back campaigns?

Tech Stack & Tools
Language: Python
Data Processing & SQL Engine: `pandas`, `DuckDB`
Data Visualization: `Plotly Express`, `Seaborn`, `Matplotlib`
Environment: Google Colab

---

Visual Highlights & Analytical Findings

1. Cohort Retention Matrix (12-Month Drop-Off)
Finding: Customer retention drops significantly from 100% (Month 0) down to ~15–35% in Month 1, stabilizing near 10–25% in long-term months.
Recommendation: Focus marketing automation on an optimized 30-day post-purchase onboarding sequence to reduce initial churn.

---

2. Strategic RFM Segmentation
Customers were scored (1-5) on Recency, Frequency, and Monetary metrics using DuckDB percentile windowing and categorized into strategic buckets:

Champions: High spenders with recent purchases. Generates the vast majority of cumulative business revenue.
At Risk: High-volume historic spenders who have not purchased in over 200–600 days. Immediate targets for win-back campaigns.
Promising / Recent: Newly onboarded buyers requiring 2nd-purchase incentive discounts.
Lost / Inactive: Largest customer count segment; lower priority for ad spend retargeting.

---

How to Run the Notebook
You can open and run this project directly in Google Colab:

[[Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Disha-kp/customer-retention-rfm-analysis/blob/main/notebooks/Customer_Retention_RFM_Analysis.ipynb)
