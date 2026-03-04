# 📊 AI Risk Decisioning System

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-XGBoost-orange)
![Domain](https://img.shields.io/badge/Domain-FinTech%20Risk-green)
![Status](https://img.shields.io/badge/Project-In%20Development-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

An **AI-powered lending risk decision platform** designed to optimize credit growth while maintaining **portfolio risk limits and capital efficiency**.

This project simulates how modern financial institutions use **machine learning, financial risk modeling, and strategy simulation** to automate lending decisions.

The platform integrates:

* Credit risk modeling
* Fraud detection
* Expected loss estimation
* Capital allocation modeling
* Risk-adjusted return optimization (RAROC)
* Lending strategy simulation
* Stress testing
* Responsible AI governance
* Portfolio monitoring dashboards


---

# 🏗 System Architecture

```
Enterprise Lending Risk Decision Architecture
```

```mermaid
flowchart TD

subgraph Data_Layer["Data Layer"]
A1[Loan Applications]
A2[Credit Bureau Data]
A3[Customer Financial Data]
A4[Transaction Data]
end

subgraph Data_Processing["Data Processing & Feature Engineering"]
B1[Data Cleaning]
B2[Feature Engineering]
B3[Feature Store]
end

subgraph Risk_Modeling["Risk Modeling Layer"]
C1[Credit Risk Model<br>PD Estimation]
C2[Fraud Detection Model]
end

subgraph Financial_Intelligence["Financial Intelligence Layer"]
D1[Expected Loss Engine<br>PD × LGD × EAD]
D2[Capital Modeling<br>RWA Simulation]
D3[RAROC Engine]
end

subgraph Strategy_Layer["Strategy & Optimization"]
E1[Strategy Simulator]
E2[Risk-Based Pricing]
E3[Portfolio Optimization]
end

subgraph Decision_Layer["Decision Engine"]
F1[Approval Rules]
F2[Reject Rules]
F3[Manual Review Queue]
end

subgraph Governance["Responsible AI Governance"]
G1[Explainability<br>SHAP]
G2[Bias Monitoring]
G3[Policy Compliance]
end

subgraph Monitoring["Monitoring & Analytics"]
H1[Model Drift Monitoring]
H2[Performance Tracking]
H3[Portfolio Risk Dashboard]
end

A1 --> B1
A2 --> B1
A3 --> B1
A4 --> B1

B1 --> B2
B2 --> B3

B3 --> C1
B3 --> C2

C1 --> D1
C2 --> F1

D1 --> D2
D2 --> D3

D3 --> E1
E1 --> E2
E2 --> E3

E3 --> F1

F1 --> F2
F1 --> F3

F1 --> G1
G1 --> G2
G2 --> G3

F1 --> H1
H1 --> H2
H2 --> H3
```

---

# 🚀 Key System Modules

## 1️⃣ Credit Risk Modeling

Predict **probability of default (PD)** using machine learning.

Models implemented:

* Logistic Regression
* Random Forest
* XGBoost

Evaluation metrics:

* AUC
* KS Statistic
* Precision / Recall

---

## 2️⃣ Fraud Detection System

Detect suspicious or fraudulent loan applications.

Outputs:

* Fraud probability score
* Fraud alert classification

---

## 3️⃣ Expected Loss Engine

Expected loss is calculated using the standard banking formula.

```
Expected Loss = PD × LGD × EAD
```

Where:

| Variable | Meaning                |
| -------- | ---------------------- |
| PD       | Probability of Default |
| LGD      | Loss Given Default     |
| EAD      | Exposure at Default    |

Outputs:

* Loan-level expected loss
* Portfolio expected loss

---

## 4️⃣ Capital Modeling

Simulates regulatory capital requirements.

```
RWA = Exposure × Risk Weight
Capital Required = RWA × Capital Ratio
```

Outputs:

* Risk-weighted assets
* Capital utilization
* Capital efficiency metrics

---

## 5️⃣ RAROC Engine

Risk Adjusted Return on Capital evaluates whether lending strategies generate economic value.

```
RAROC =
(Net Interest Income − Expected Loss − Operating Cost)
/ Capital Required
```

Used for **strategy comparison and portfolio optimization**.

---

## 6️⃣ Strategy Simulator

Simulates multiple lending strategies.

### Aggressive Growth

Higher approvals, higher risk.

### Conservative Filtering

Lower approvals, safer portfolio.

### Risk-Based Pricing

Interest rates adjusted to borrower risk.

Outputs:

* Portfolio NPA
* Expected loss
* Revenue
* Capital usage
* RAROC

---

## 7️⃣ Stress Testing Simulator

Evaluates portfolio resilience during economic downturns.

| Scenario      | PD Change | LGD Change |
| ------------- | --------- | ---------- |
| Base Case     | 0%        | 0%         |
| Mild Stress   | +15%      | +5%        |
| Severe Stress | +35%      | +15%       |

Outputs:

* Expected loss under stress
* Capital impact
* Portfolio stability

---

## 8️⃣ Decision Engine

Combines risk signals to generate automated lending decisions.

Inputs:

* Credit risk score
* Fraud risk score
* Risk policy thresholds

Possible outcomes:

* Approve
* Reject
* Manual review

---

## 9️⃣ Responsible AI Governance

Ensures fairness and transparency.

Includes:

* SHAP explainability
* Feature importance
* Bias monitoring
* Fairness checks

---

## 🔟 Monitoring Dashboard

Tracks performance after deployment.

Monitors:

* Model drift
* PD distribution shifts
* Performance decay
* Manual override decisions

---

# 📊 Interactive Risk Command Center

The system includes a **Streamlit dashboard** for exploring the platform.

Features:

* KPI tracking
* Model comparison
* Strategy simulator
* Stress testing
* Portfolio analytics
* Project execution tracker

Run locally:

```bash
streamlit run final_bfsi_project_command_center_v3.py
```

---

# 📂 Project Structure

```
ai-risk-decisioning-system

01_data/
datasets used for training models

02_notebooks/
01_data_preprocessing.ipynb
02_credit_risk_model.ipynb
03_fraud_detection.ipynb
04_expected_loss_capital_model.ipynb
05_strategy_simulator.ipynb
06_stress_testing.ipynb

03_models/
trained ML models

04_financial_engine/
expected_loss.py
capital_model.py
raroc_engine.py

05_decision_engine/
approval_rules.py

06_stress_testing/
stress_simulator.py

07_governance/
bias_monitor.py
explainability.py

08_dashboard/
command_center.py

09_docs/
architecture_diagram.png
demo.gif

README.md
requirements.txt
```

---

# 📚 Datasets Used

Public lending datasets used for modeling.

* Home Credit Default Risk
* LendingClub Loan Data
* Give Me Some Credit

These datasets provide structured borrower information for credit risk modeling.

---

# 🧰 Technologies Used

Programming

* Python

Machine Learning

* Scikit-learn
* XGBoost

Data Processing

* Pandas
* NumPy

Visualization

* Matplotlib
* Streamlit

Explainability

* SHAP

---

# 🎯 Target Performance Metrics

| Metric              | Target |
| ------------------- | ------ |
| AUC                 | ≥ 0.80 |
| KS Statistic        | ≥ 0.40 |
| Portfolio NPA       | ≤ 5%   |
| RAROC               | ≥ 18%  |
| Capital Utilization | < 85%  |

---

# 🔮 Future Improvements

Possible extensions include:

* Real-time lending decision API
* Reinforcement learning for strategy optimization
* Advanced capital stress testing
* Dynamic portfolio allocation
* Regulatory compliance simulation

---

# 👩‍💻 Author

**Hiral Sarkar**

AI & Risk Analytics Enthusiast
Building **AI-driven financial decision systems for banking and fintech**.

---

# 📜 License

This project is intended for **educational and portfolio demonstration purposes**.

---

## ⭐ If you find this project interesting, consider starring the repository!

---
