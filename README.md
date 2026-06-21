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

## Executive Summary & Business Strategy

Beyond standard descriptive statistics, this analysis uncovers the latent variables driving customer attrition and formulates actionable retention architectures:

### 1. Product Asymmetry (Demographics vs. Infrastructure)
* **Finding:** Senior Citizens have a 2x higher churn probability, and Fiber Optic services contribute to the highest attrition rate (42%).
* **Diagnosis:** A technical literacy gap. Seniors on Fiber Optic networks are highly susceptible to churn when facing minor technical issues due to a lack of automated or prioritized support.
* **Recommendation:** Deploy automated, zero-cost `TechSupport` routing specifically for the senior demographic on Fiber Optic plans to prevent operational panic and subsequent service cancellation.

### 2. Redefining Loyalty (Survivorship Bias & Trailing Indicators)
* **Finding:** Correlation matrices show high `tenure` is inversely related to churn risk.
* **Diagnosis:** `Tenure` is a trailing indicator, not a causal metric. The near-zero churn in high-tenure cohorts is a manifestation of *Survivorship Bias* — they remained because their local network infrastructure happened to be stable. Passive customers who continue paying are trapped in *Customer Inertia*, not necessarily loyal.
* **Recommendation:** Cease relying on `tenure` as a safety metric. Shift focus to proactive Quality of Service (QoS) monitoring in regions showing high first-month churn spikes.

### 3. Financial Retention Architecture (LTV vs. ARPU)
* **Finding:** Month-to-month (MTM) customers generate the highest median revenue ($79 to $111+) but possess the maximum churn probability (43%). 
* **Diagnosis:** Offering cash discounts to retain these high-risk entities is a financial flaw that destroys Average Revenue Per User (ARPU).
* **Recommendation:** Execute *Ecosystem Lock-in*. Mandate an upgrade to a 1-year contract, compensated purely through the injection of Value-Added Services (VAS) such as priority tech support or streaming bundles. This sacrifices marginal Customer Acquisition Cost (CAC) to secure massive Customer Lifetime Value (LTV) cash flow.(Online Security, Tech Support) are strongly associated with lower churn rates

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
#