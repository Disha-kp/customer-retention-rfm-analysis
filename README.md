Customer Retention & RFM Segmentation Analysis

BUSINESS PROBLEM: A retail/SAAS business wants to identify who its most valuable customers are, detect drop-off(churn) early, and undertsnad how customer retention evolves ovr time 

This is an end-to-end data analytics project evaluating customer purchase patterns, cohort retention dynamics, and strategic customer segmentation using Python, DuckDB (SQL), and Plotly.

Project Overview
This project analyzes online retail transaction data to identify retention drop-off points and build strategic RFM (Recency, Frequency, Monetary) segments. 

Tech Stack & Tools
Language: Python
Data Processing & SQL Engine: `pandas`, `DuckDB`
Data Visualization: `Plotly Express`, `Seaborn`, `Matplotlib`
Environment: Google Colab

Key Business Questions Addressed:
1. What is the month-over-month customer retention drop-off rate?
2. How is total revenue distributed across customer loyalty tiers?
3. Which high-value customers are currently **At Risk** of churn and require targeted win-back campaigns?

This is how I aligned "Customer Retention & RFM Segmentation Analysis" project with each of the following steps:

1. Ask

Core Questions Identified: 
How does customer retention decay month-over-month following initial onboarding?
How is business revenue distributed across different customer behavioral tiers?
Which high-spending customers are currently "At Risk" and require proactive retention interventions?

Key Stakeholders: Marketing Team (for retention campaigns), Customer Success, and Executive Leadership (for LTV forecasting).

2.  Prepare

Data Source: UCI Online Retail II Dataset loaded via Kaggle into Google Colab.
Data Attributes: Transactional record containing `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.
Data Privacy & Security: Anonymized customer IDs evaluated in an isolated cloud notebook environment (Google Colab).
Storage & Structuring: Downloaded, formatted, and staged using Pandas DataFrames for downstream manipulation.

3. Process

Data Cleaning:
Filtered out canceled transactions (`InvoiceNo` starting with 'C') and negative/zero quantities.
Dropped null `CustomerID` records to ensure accurate cohort tracking.
Extracted purchase month identifiers (`CohortMonth` and `InvoiceMonth`).

Aggregation & Transformation:
Engineered Monetary Value (`Quantity` $\times$ `UnitPrice`).
Used DuckDB (SQL) window functions to compute customer-level Recency (days since last purchase), Frequency (total orders), and Monetary metrics.
Data Export: Output cleaned transaction logs (`cleaned_retail_data.csv.gz`) and calculated customer metrics (`rfm_segmented_data.csv`).

4. Analyze

Cohort Analysis: Tracked monthly customer cohorts from Month 0 through Month 12+ to measure retention rates over time.
RFM Scoring: Evaluated customers on Recency, Frequency, and Monetary scores (scale 1–5 using percentiles via SQL) to assign strategic labels (Champions, Loyal Customers, Promising, At Risk, Lost/Inactive).
Key Findings:
Sharp Initial Churn: Customer retention drops from **100% (Month 0)** to **~15–35% in Month 1**, stabilizing between 10–25% in subsequent months.
Revenue Concentration: A small fraction of customers (*Champions*) accounts for the vast majority of cumulative revenue.
Slipping High Spenders: Identified a key cluster of historic high-spenders who have not purchased in 200–600+ days (At Risk).

5. Share

Data Visualization: Built an interactive suite of Plotly visuals:
Heatmap: 12-Month Cohort Retention Matrix.
Treemap & Bar Chart: Revenue and customer volume distribution across RFM tiers.
Scatter Plot: Recency vs. Monetary spend bubble chart.

Portfolio Publishing: Published the complete, end-to-end project on **GitHub** (`customer-retention-rfm-analysis`), structured with a documentation `README.md`, reproducible code, compressed datasets, and visual screenshots.

6. Act

Post-Purchase Onboarding (Month 1): Deploy an automated 30-day email onboarding sequence and a second-purchase incentive within 14 days to smooth out the massive Month 1 retention drop-off.

Win-Back Campaigns (At Risk Tier): Launch targeted re-engagement campaigns (personalized discounts, product recommendations) for high-value spenders slipping past 200+ days of inactivity.

VIP Loyalty Program (Champions): Implement an exclusive VIP program (early product access, dedicated perks) to retain top-tier revenue drivers.

Ad Spend Optimization (Lost/Inactive*): Exclude long-term inactive users from paid retargeting ads to cut acquisition/retargeting costs.

Visual Highlights & Analytical Findings

1. Cohort Retention Matrix (12-Month Drop-Off)
Finding: Customer retention drops significantly from 100% (Month 0) down to ~15–35% in Month 1, stabilizing near 10–25% in long-term months.
Recommendation: Focus marketing automation on an optimized 30-day post-purchase onboarding sequence to reduce initial churn.

2. Strategic RFM Segmentation
Customers were scored (1-5) on Recency, Frequency, and Monetary metrics using DuckDB percentile windowing and categorized into strategic buckets:

Champions: High spenders with recent purchases. Generates the vast majority of cumulative business revenue.
At Risk: High-volume historic spenders who have not purchased in over 200–600 days. Immediate targets for win-back campaigns.
Promising / Recent: Newly onboarded buyers requiring 2nd-purchase incentive discounts.
Lost / Inactive: Largest customer count segment; lower priority for ad spend retargeting.

How to Run the Notebook
You can open and run this project directly in Google Colab:

[[Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Disha-kp/customer-retention-rfm-analysis/blob/main/notebooks/Customer_Retention_RFM_Analysis.ipynb)
