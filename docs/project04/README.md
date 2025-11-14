# Project 4 – Titanic Regression (Predicting Fare)

**Author:** Womenker Karto  
**Date:** 2025-11-14  

## Introduction
This project uses the Titanic dataset to predict the **fare** (continuous target) using regression models. The goal is to explore relationships between passenger characteristics and ticket price, evaluate multiple regression models, and understand how model complexity and feature selection impact performance.  

We explore four feature cases:  
1. **Case 1 – Age only**  
2. **Case 2 – Family Size only**  
3. **Case 3 – Age + Family Size**  
4. **Case 4 – Age + Family Size + Sex + Pclass**  

A bonus section applies the same regression process to the **Tips dataset** from `seaborn` for additional practice and extra credit.

---

## Dataset
The dataset is loaded directly from the `seaborn` library:  

```python
import seaborn as sns
titanic = sns.load_dataset('titanic')
```
Key preprocessing steps included:  
- Filling missing `age` values with the median.  
- Dropping rows with missing `fare`.  
- Feature engineering: creating `family_size` from `sibsp` + `parch` + 1.  
- Converting categorical features (`sex`, `pclass`) to numeric values for regression.  

---

## Methodology
1. **Data Preparation** – impute missing values, convert categories to numeric, and create new features.  
2. **Feature Selection** – four feature combinations were selected to evaluate model impact.  
3. **Model Training** – Linear Regression, Ridge, ElasticNet, and Polynomial Regression (degree 3).  
4. **Evaluation** – using R², RMSE, and MAE for train and test sets.  
5. **Reflection** – analyzing model performance and insights.  

---

## Summary Table

| Model Type | Case | Features Used | R² (Test) | RMSE | MAE | Notes |
|------------|------|---------------|------------|------|-----|-------|
| Linear Regression | Case 1 | age | 0.003 | 37.97 | 25.29 | Underfitting |
| Linear Regression | Case 2 | family_size | 0.022 | 37.61 | 25.03 | Poor predictor |
| Linear Regression | Case 3 | age + family_size | 0.050 | 37.08 | 24.28 | Slight improvement |
| Linear Regression | Case 4 | age + family_size + sex + pclass | 0.399 | 29.49 | 20.08 | Best among linear models |
| Ridge Regression | Case 4 | age + family_size + sex + pclass | 0.400 | 29.47 | 20.05 | Slight regularization gain |
| ElasticNet Regression | Case 4 | age + family_size + sex + pclass | 0.429 | 28.75 | 17.39 | Balances shrinkage and feature selection |
| Polynomial Regression (deg 3) | Case 4 | age + family_size + sex + pclass | 0.506 | 26.72 | 15.05 | Captures non-linear patterns |

---

## Reflections
**Feature Insights:**  
- `Age` and `family_size` alone are poor predictors of fare.  
- Adding `sex` and `pclass` (Case 4) improves performance considerably.  

**Model Insights:**  
- Linear models provide interpretable baseline results.  
- Ridge improves slightly via regularization.  
- ElasticNet balances feature selection and coefficient shrinkage.  
- Polynomial regression (degree 3) captures some non-linear relationships and provides the best R² and lowest errors.  

**Observations:**  
- Cases 1-3 underfit the data due to insufficient feature information.  
- Case 4 consistently outperforms others, showing the importance of categorical and structural features.  
- Higher complexity models (polynomial regression) perform better but risk overfitting.  

---

## Bonus Section
**Tips Dataset Regression**  
- Dataset: `tips` from seaborn (continuous target: `total_bill`)  
- Models: Linear Regression, Ridge, ElasticNet, Polynomial Regression  
- Process: Same steps as Titanic – preprocess data, split train/test, train models, evaluate R², RMSE, and MAE.  
- Findings: Linear and Ridge models performed comparably; ElasticNet slightly improved MAE; Polynomial regression overfit due to limited data points.  
- Insights: Process can generalize to other continuous regression problems, demonstrating the flexibility of the workflow.  

---

## Next Steps / Recommendations
1. Test additional features (`pclass`, `embarked`, `deck`) for improved predictions.  
2. Apply log transformation on fare to reduce skew and improve regression fit.  
3. Explore higher-degree polynomial features cautiously to avoid overfitting.  
4. Consider other regression models such as Random Forest or Gradient Boosting for continuous targets.  
5. Extend workflow to other datasets for practice with continuous target prediction.
