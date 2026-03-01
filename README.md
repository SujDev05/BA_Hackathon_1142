Credit Score & Behavioral Risk Segmentation

📌 Project Overview

This project analyzes customer bank transaction data to identify behavioral spending patterns and generate a Behavioral Risk Score.

Using clustering and feature engineering techniques, customers are segmented into behavioral groups based on their transaction habits. A risk score is then computed to estimate impulse spending tendencies, followed by personalized behavioral nudges.

The goal of this notebook is to demonstrate how unsupervised learning and feature engineering can be applied to financial transaction data to derive meaningful customer insights.

📂 Dataset

The notebook uses:

bank_transactions.csv
Expected Key Columns

CustomerID

CustomerDOB

TransactionDate

TransactionTime

TransactionAmountINR

CustAccountBalance

⚠️ Update the file path in the notebook before running.

⚙️ Features Engineered

The following behavioral features are created:

Age – Derived from CustomerDOB and TransactionDate

Hour – Extracted from TransactionTime

Balance_Ratio – TransactionAmount / AccountBalance

Late_Night Flag – Transactions between 11PM–4AM

Weekend Flag – Transactions on Saturday/Sunday

Spend_Variability – Standard deviation of transaction amount per customer

Customer-level aggregation is performed using groupby operations.

🧠 Machine Learning Approach
1️⃣ Clustering

Algorithm: K-Means

Features scaled using StandardScaler

Number of clusters: 4

Purpose: Segment customers by behavioral patterns

2️⃣ Risk Score Calculation

A composite Risk Score (0–100) is computed using:

Balance_Ratio

Spend_Variability

Late_Night frequency

Weekend frequency

Steps:

Normalize features using MinMaxScaler

Take mean of normalized values

Multiply by 100

📊 Visualizations

The notebook includes:

Boxplots (Cluster vs Balance Ratio)

Boxplots (Cluster vs Risk Score)

Heatmap (Cluster behavior summary)

Histogram of Risk Score distribution

PCA-based 2D projection for cluster visualization

💬 Behavioral Nudges

Based on Risk Score:

Risk Score	Nudge
> 70	High impulse tendency – Recommend spending alerts
40–70	Moderate impulse behaviour – Suggest budgeting tools
< 40	Low impulse behaviour – Financial habits stable
🛠️ Tech Stack

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

▶️ How to Run

Install dependencies:

pip install pandas numpy matplotlib seaborn scikit-learn

Update dataset path inside the notebook:

df = pd.read_csv("path/to/bank_transactions.csv")

Run all cells sequentially.
