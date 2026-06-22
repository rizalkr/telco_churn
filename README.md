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
* **Finding:** Senior Citizens show a significantly higher churn probability, and Fiber Optic services contribute to the highest attrition rate (42%).
* **Diagnosis:** High likelihood of a confounding variable: Fixed Income alongside a technical literacy gap. Seniors on premium Fiber Optic networks have higher price sensitivity. Churn in this demographic often stems from financial strain coupled with frustration over minor technical issues, rather than just operational panic.
* **Recommendation:** Deploy a dual-pronged mitigation routing. Implement automated, zero-cost `TechSupport` prioritization for the senior demographic. Concurrently, design proactive algorithms to offer seamless downgrades to more affordable DSL or lower-bandwidth plans before financial strain triggers a complete service cancellation.

### 2. Redefining Loyalty (Survivorship Bias & Trailing Indicators)
* **Finding:** Correlation matrices indicate high `tenure` is inversely related to churn risk.
* **Diagnosis:** Viewing `tenure` purely as a causal metric introduces analytical risk. The low churn in high-tenure cohorts largely reflects *Survivorship Bias* (they remained due to stable local infrastructure) and *Customer Inertia* (passive continuation). Passive customers are trapped in inertia, which is valuable but distinct from active loyalty.
* **Recommendation:** Repurpose `tenure` as a probability weighting parameter rather than a standalone safety metric. Shift focus to proactive Quality of Service (QoS) monitoring in regions showing high first-month churn spikes, while executing low-friction maintenance to sustain the inertia of high-tenure cohorts.

### 3. Financial Retention Architecture (LTV vs. ARPU)
* **Finding:** Month-to-month (MTM) customers generate high median revenue ($79 to $111+) but present a critical churn probability (43%). 
* **Diagnosis:** Reacting to MTM churn risk by deploying direct cash discounts degrades Average Revenue Per User (ARPU) and merely delays attrition. The structural vulnerability is the lack of exit friction; MTM customers can leave without penalty.
* **Recommendation:** Implement *Strategic Ecosystem Lock-in* via Choice Architecture. Shift the retention mechanism from financial reduction to value addition. Offer premium Value-Added Services (VAS)—specifically `Online Security` or `Priority Tech Support`, which strongly correlate with lower churn rates—at zero cost, strictly under the condition that the customer upgrades to a 1-year contract. This frames the transition as an organic customer upgrade, trading marginal short-term costs to secure long-term Customer Lifetime Value (LTV).
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