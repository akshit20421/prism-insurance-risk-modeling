# PRISM: Predictive & Research-based Insurance Statistical Modeling

## Overview
PRISM is an end-to-end insurance pricing system that models claim frequency and severity using statistically interpretable models, benchmarks against machine learning, and applies causal inference to identify true risk drivers.

The project demonstrates how insurers can price risk fairly, accurately, and transparently.

---

## Key Components

### 1. Frequency Modeling
- Poisson and Negative Binomial Generalized Linear Models (GLMs)  
- Exposure offsets for policy duration  
- Model selection using deviance diagnostics and AIC  

### 2. Severity Modeling
- Gamma GLM with log link  
- Right-skewed cost modeling  
- Interpretable claim cost estimation  

### 3. Pure Premium Pricing
Pure Premium represents the expected claim cost per policy and is constructed using a frequency–severity decomposition:
Pure Premium=E(Claim Frequency)×E(Claim Severity)
Where:

Claim Frequency is modeled using a Negative Binomial GLM with exposure offsets
Claim Severity is modeled using a Gamma GLM with log link
This approach mirrors industry actuarial pricing practice and produces an interpretable, statistically valid insurance pricing framework.

### 4. Machine Learning Benchmarking
- XGBoost regression for claim frequency  
- Comparison against GLM using mean Poisson deviance  
- Trade-off between accuracy and interpretability  

### 5. Causal Inference
- Propensity score weighting  
- Identification of causal risk drivers  
- Fairness and regulatory justification  

### 6. Risk Segmentation
- Business-ready pricing strategy  
- Five risk bands with 18× cost separation  

---

## Results

- Negative Binomial GLM selected for claim frequency  
- Gamma GLM selected for claim severity  
- XGBoost improves performance by ~3%, but GLM retained for stability  
- Bonus–Malus shown to have a causal impact on claim risk  
- Very-high-risk policies cost ~18× more than very-low-risk  

---

## Repository Structure

notebooks/
- 01_data_audit_and_eda.ipynb
- 02_frequency_glm.ipynb
- 03_severity_glm.ipynb
- 05_ml_benchmarking.ipynb
- 06_causal_analysis.ipynb
- 07_risk_segmentation.ipynb

data/
-README.md

report/
- (Executive summary coming soon)


---

## Why This Project Matters

This project mirrors real insurance pricing workflows and demonstrates:

- Statistical modeling discipline  
- Machine learning maturity  
- Causal reasoning  
- Business decision making  

It is suitable for roles in Data Science, Machine Learning, Actuarial Science, and Risk Analytics.

---

## Getting Started

1. Download the French Motor Third Party Liability Claims dataset  
2. Place `freMTPL2freq.csv` and `freMTPL2sev.csv` inside `data/`  
3. Run notebooks in order from `01` to `07`

---

## Author

Akshit Gupta 
