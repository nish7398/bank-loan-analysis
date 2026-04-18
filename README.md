# 🏦 Bank Loan Risk Analysis

> End-to-end risk analysis of 30,000 real Lending Club loans — identifying default patterns, segmenting borrowers by risk tier, and building a custom risk scoring formula using Python.

---

## 📌 Project Overview

This project analyzes **real loan data from Lending Club (2007–2018)** — one of the largest peer-to-peer lending platforms in the US. Using a sample of 30,000 completed loans drawn from 1.3 million records, the analysis answers critical risk questions that a bank's credit team would ask before approving or pricing a loan.

**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn  
**Skills:** Data Cleaning · EDA · Risk Segmentation · Default Analysis · Custom Scoring Formula · Financial Analytics

---

## 🎯 Business Questions Answered

| # | Question | Business Use |
|---|----------|-------------|
| 1 | How does loan grade affect default rate? | Credit risk pricing |
| 2 | Which loan purposes carry the highest risk? | Loan approval policy |
| 3 | Do defaulters have higher interest rates & DTI? | Underwriting criteria |
| 4 | How has default rate trended from 2007–2018? | Portfolio risk monitoring |
| 5 | Which features correlate most with defaults? | Risk model inputs |
| 6 | How can borrowers be segmented by risk tier? | Customer segmentation |
| 7 | Which states have the highest default rates? | Geographic risk mapping |
| 8 | Can a custom risk score predict defaults? | Risk scoring model |

---

## 📁 Repository Structure

```
bank-loan-analysis/
│
├── data/
│   ├── loan_sample.csv          # 30,000 real Lending Club loans
│   └── loan_cleaned.csv         # Cleaned output with risk score
│
├── notebooks/
│   └── BANK_loan_analysis.ipynb # Full analysis (12 steps)
│
├── visualizations/
│   ├── 01_grade_risk_analysis.png
│   ├── 02_purpose_risk_analysis.png
│   ├── 03_financial_metrics_comparison.png
│   ├── 04_yearly_trends.png
│   ├── 05_risk_correlation_heatmap.png
│   ├── 06_risk_segmentation.png
│   ├── 07_state_default_rates.png
│   └── 08_risk_score_analysis.png
│
└── README.md
```

---

## 🔧 Data Cleaning Steps

| Issue | Action |
|-------|--------|
| `int_rate` stored as string with % | Stripped % and converted to float |
| `revol_util` stored as string with % | Stripped % and converted to float |
| `term` stored as "36 months" | Extracted integer |
| Numerical missing values | Filled with column median |
| Categorical missing values | Filled with 'Unknown' |
| `issue_d` stored as "Jan-2015" | Parsed to datetime, extracted year/month |
| `emp_length` as text categories | Mapped to numeric scale (0–10) |
| Binary target variable missing | Created `is_default` flag from loan_status |

**Result:** 30,000 clean records with 0 nulls, consistent data types, and enriched features.

---

## 📊 Key Findings

| # | Finding | Detail |
|---|---------|--------|
| 1 | **Overall default rate: 21.33%** | 1 in 5 loans ends in default or late payment |
| 2 | **Grade A → 6.4% default, Grade G → 50.2%** | Grade is the single strongest risk predictor |
| 3 | **Small business loans most risky** | 33.1% default rate vs 22.4% for debt consolidation |
| 4 | **Defaulters pay higher interest** | Avg 15.8% vs 12.9% for fully paid loans |
| 5 | **DTI weakly correlates with default** | High DTI increases risk but isn't decisive alone |
| 6 | **Interest rate most correlated with default** | r = 0.23 — strongest numeric predictor |
| 7 | **Loan volume grew 10x from 2008–2015** | Platform scaled rapidly post-financial crisis |
| 8 | **Custom risk score validates segmentation** | Very High risk band: 45%+ actual default rate |

---

## 🔑 Advanced Features

**Custom Risk Score (0–100)**
A weighted formula built from EDA findings:
- Loan grade (0–40 pts) — highest weight, strongest predictor
- Debt-to-income ratio (0–20 pts)
- Delinquency history (0–20 pts)
- Interest rate tier (0–10 pts)
- Revolving utilization (0–10 pts)

**Borrower Risk Segmentation**
5-tier classification (Low → Very High) based on grade, DTI, and delinquency — validated against actual default rates.

**State-wise Geographic Risk**
Default rates mapped across US states to identify geographic concentration risk.

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/nish7398/bank-loan-analysis.git
cd bank-loan-analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch notebook
jupyter notebook notebooks/BANK_loan_analysis.ipynb
```

Run all cells in order. Cleaned data and 8 visualizations will auto-save.

---

## 🧠 What I'd Add Next

- **Logistic Regression Model** — Predict default probability using scikit-learn
- **Tableau Dashboard** — Interactive risk heatmap, grade performance, state map
- **Cohort Analysis** — Track default rates by loan origination year
- **Feature Importance** — Use Random Forest to rank risk predictors

---

## 📬 Connect

**Nishant Jaiswal** — Data Analyst  
[LinkedIn](https://www.linkedin.com/in/nishant-jaiswal01) · [Email](mailto:nishant.jais3918@gmail.com)
