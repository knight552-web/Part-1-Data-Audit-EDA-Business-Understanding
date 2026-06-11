# 📊 D2C Customer Churn — Part 1: Data Audit & Business Understanding

## 🧠 Project Overview

This repository contains Part 1 of the D2C Customer Churn Capstone Project.

The objective of this phase is to:
- audit the raw datasets,
- perform exploratory data analysis (EDA),
- identify churn-risk patterns, and
- translate findings into business insights.

This analysis forms the foundation for segmentation, modeling, and deployment in later parts.

---

## 📁 Repository Structure

project/
 eda_audit.ipynb
│
├── data_quality_report.md
├── business_memo.md
├── requirements.txt
└── README.md

---

## 📦 Dataset Description

The dataset represents a D2C personal-care brand and includes:

- Customer profiles
- Order history
- Support tickets
- Web/app activity
- Campaign/intervention history
- Churn labels

Snapshot Date: 2025-09-30  
Target Definition: No purchase in next 60 days = churn

---

## ⚠️ Important Assumptions & Constraints

### 🚫 Data Leakage Prevention

Only data available on or before the snapshot date (2025-09-30) is used for analysis.

- Post-snapshot orders are excluded from feature engineering.
- These are used only for churn label generation.

---

## 🔍 Analysis Workflow

The notebook `eda_audit.ipynb` follows this structured approach:

1. Data Loading & Schema Inspection
2. Data Quality Audit
3. Feature Engineering
4. Exploratory Data Analysis

---

## 📊 Key Insights

- Recency is the strongest churn driver
- Lower spending customers churn more frequently
- Negative sentiment is widespread
- Engagement decline strongly correlates with churn

---

## ⚙️ Setup Instructions

### Install dependencies

pip install -r requirements.txt

### Run notebook

jupyter notebook notebooks/eda_audit.ipynb

---

## 👤 Author

Adrian Dsouza  
Capstone Project — D2C Customer Churn Intelligence
