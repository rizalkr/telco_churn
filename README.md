# Telco Customer Churn — Exploratory Data Analysis

A data analytics portfolio project performing a full exploratory data analysis (EDA) on the IBM Telco Customer Churn dataset to uncover the key drivers of customer churn.

---

## Overview

Customer churn — the rate at which customers stop doing business with a company — is one of the most critical metrics for subscription-based businesses. This project analyzes a telecom dataset to answer the core business question:

> **"Who is at risk of churning, and what factors drive that decision?"**

---

## Dataset

| Attribute | Details |
|-----------|---------|
| **Source** | [IBM Telco Customer Churn — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) |
| **Records** | 7,043 customers |
| **Features** | 21 columns (demographics, services, contract, charges) |
| **Target** | `Churn` (Yes / No) |

### Key Features

- **Demographics**: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
- **Services**: `PhoneService`, `InternetService`, `OnlineSecurity`, `TechSupport`, `StreamingTV`, etc.
- **Contract**: `Contract`, `PaperlessBilling`, `PaymentMethod`
- **Financial**: `tenure`, `MonthlyCharges`, `TotalCharges`

---

## Analysis Structure

The notebook is organized into 9 sections:

1. **Setup & Libraries** — Import dependencies and configure plot styling
2. **Data Loading & Cleaning** — Type conversion, missing value handling, feature prep
3. **Target Distribution** — Churn vs. retained class balance
4. **Demographic Analysis** — Churn rate by gender, senior status, partner, dependents
5. **Services Analysis** — Churn rate across 9 service types
6. **Contract & Payment Analysis** — Impact of contract length and payment method
7. **Financial Analysis** — Tenure, monthly charges, and total charges distributions
8. **Correlation & Heatmap** — Linear relationships between numeric features
9. **Summary & Business Insights** — Consolidated findings and recommendations

---

## Key Findings

- **26.5% overall churn rate** — dataset is moderately imbalanced
- **Fiber Optic** customers churn at ~42%, vs. DSL at ~19% and no-internet at ~7%
- **Month-to-month contracts** carry a ~43% churn rate, vs. ~3% for two-year contracts
- **Churned customers** had a median tenure of only **10 months**, compared to **37 months** for retained customers
- **Senior citizens** churn at approximately **2x the rate** of non-senior customers
- **Add-on services** (Online Security, Tech Support) are strongly associated with lower churn rates

---

## Visualizations

| Chart | Description |
|-------|-------------|
| `eda_01_churn_distribution.png` | Churn vs. retained bar and donut chart |
| `eda_02_demographics.png` | Churn rate by demographic factors |
| `eda_03_services.png` | Churn rate across all service types |
| `eda_04_contract_payment.png` | Churn rate by contract and payment method |
| `eda_05_financial.png` | Histograms and boxplots of numeric variables |
| `eda_06_correlation.png` | Correlation heatmap of numeric features |

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.12 | Core language |
| pandas | Data manipulation |
| numpy | Numerical computation |
| matplotlib | Base visualization |
| seaborn | Statistical visualization |
| Jupyter Notebook | Interactive analysis environment |

---

## How to Run

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd porto-analitik

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch Jupyter
jupyter notebook telco_churn.ipynb
```

---

## Next Steps

- **Feature Engineering**: Create new features such as tenure groups and charge-to-tenure ratios
- **Predictive Modeling**: Build classification models (Logistic Regression, Random Forest, XGBoost) to predict at-risk customers
- **Business Action**: Focus retention strategies on new Fiber Optic customers on month-to-month plans — the highest-risk segment identified in this analysis

---

*Created as part of a data analytics portfolio.*
