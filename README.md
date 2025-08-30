# Household Risk Factors for Multi-Drug Resistance (MDR) A Machine Learning Approach in LMIC Contexts

## Project Overview
This project investigates household-level risk factors for  multi-drug resistance (MDR) in low- and middle-income countries (LMICs).  
We combine exploratory data analysis (EDA), supervised machine learning models, hyperparameter and threshold tuning, and interpretability methods (coefficients and SHAP).  

The main objective is to minimize false negatives (high recall), which is critical for public health decision-making.  

Key signals identified:
- Boiling milk → protective  
- Milk consumption → increases MDR risk  
- Eating diseased animals → increases MDR risk  
- Education → slightly protective  
- Antibiotic use (abruse) → minor effect  

---

## Repository
- **Household Risk Factors for Multi-Drug Resistance A Machine Learning Approach in LMIC Contexts.ipynb**  
  Main notebook containing EDA, modeling, tuning, interpretability, and evaluation.  

- **AMR_data.csv**  
  Input dataset (household-level).  

- **saved_models/**  
  Contains:
  - Trained models (Logistic Regression, Random Forest, XGBoost, LightGBM, CatBoost, Decision Tree)  
  - GridSearch best pipelines (recall and F2 optimized)  
  - Logistic Regression with tuned threshold (final chosen model)  
  - CSV exports of model performance results  

---

## Key Results (Test Set)
**Chosen model:** Logistic Regression with threshold = 0.38  

- Recall: 86.3%  
- Precision: 75.7%  
- F₂: 0.84 (recall-weighted)  
- ROC-AUC: ~0.875  
- PR-AUC: ~0.893  
- Confusion Matrix: `[[TN=270, FP=123], [FN=61, TP=384]]`  

**Why this model?**  
It provided the best balance for minimizing false negatives while staying fast and interpretable.  

---

## Top Predictors (LogReg)
| Feature                  | Effect on MDR |
|--------------------------|---------------|
| Boiling milk             | Protective ↓  |
| Milk consumption         | Risk ↑        |
| Eating diseased animals  | Risk ↑        |
| Education                | Protective ↓  |
| Antibiotic use (abruse)  | Minor effect  |

---

## Future Enhancements
- Validate on larger, more diverse datasets  
- Add socio-economic and environmental features  
- Develop a simple interface for practical screening use  
- Explore cost-sensitive learning to further penalize false negatives  

---

## Author
Jonathan mark H · 2025
