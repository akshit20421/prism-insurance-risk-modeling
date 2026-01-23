# PRISM  
## Predictive & Research-based Insurance Statistical Modeling  
### Executive Summary

---

## 1. Problem Statement

Insurance pricing requires accurate estimation of risk while maintaining transparency, fairness, and regulatory compliance.  
Many modern machine learning models offer strong predictive performance but lack interpretability, making them difficult to deploy in regulated environments.

This project addresses the question:

**How can insurance risk be priced accurately, fairly, and transparently using statistical and machine learning methods?**

---

## 2. Data Overview

The analysis uses the French Motor Third Party Liability Claims dataset, consisting of:

- Policy-level exposure and risk factors  
- Claim counts for frequency modeling  
- Claim amounts for severity modeling  

Frequency and severity are modeled separately following standard actuarial practice.

---

## 3. Methodology

### 3.1 Claim Frequency Modeling
- Poisson and Negative Binomial Generalized Linear Models (GLMs)
- Exposure offsets to account for policy duration
- Model selection using deviance diagnostics and AIC

### 3.2 Claim Severity Modeling
- Gamma GLM with log link
- Suitable for positive, right-skewed claim cost distributions

### 3.3 Pure Premium Pricing
Pure Premium is constructed using a frequency–severity decomposition:

Pure Premium=E(Claim Frequency)×E(Claim Severity) 
This provides an interpretable estimate of expected claim cost per policy.

---

## 4. Machine Learning Benchmark

- XGBoost regression was used to benchmark claim frequency prediction
- Performance evaluated using mean Poisson deviance
- ML improved predictive accuracy by approximately 3%

Despite the improvement, GLMs were retained for production use due to interpretability, stability, and regulatory suitability.

---

## 5. Causal Analysis

Propensity score weighting was applied to assess whether Bonus–Malus is a causal risk driver.

Results show that high Bonus–Malus policies have a **3.5 percentage point higher probability of claims**, after adjusting for confounding factors.

This provides evidence that Bonus–Malus has a causal impact on claim risk and is a justified pricing factor.

---

## 6. Risk Segmentation

Policies were segmented into five risk bands based on pure premium:

- Very Low Risk  
- Low Risk  
- Medium Risk  
- High Risk  
- Very High Risk  

Very-high-risk policies exhibit approximately **18× higher expected claim cost** than very-low-risk policies, demonstrating strong risk differentiation and pricing fairness.

---

## 7. Business Impact

This framework enables insurers to:

- Price risk accurately using statistically sound models  
- Maintain transparency and regulatory compliance  
- Justify pricing factors using causal evidence  
- Translate model outputs into actionable pricing strategies  

---

## 8. Conclusion

PRISM demonstrates how statistical modeling, machine learning, and causal inference can be combined into a production-ready insurance pricing system.

The project mirrors real-world actuarial and data science workflows and is suitable for applications in insurance analytics, risk management, and applied machine learning.

