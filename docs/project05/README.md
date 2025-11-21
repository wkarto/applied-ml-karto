# Project 5 – Ensemble Machine Learning (Wine & Spiral Classification)

**Author:** Womenker Karto  
**Date:** 2025-11-21 

## Introduction
This project explores the application of Ensemble Machine Learning techniques to solve classification problems using two datasets: the Wine dataset and a non-linear Spiral dataset. The primary objective is to evaluate how ensemble models improve predictive performance compared to traditional single classifiers, particularly in scenarios involving complex decision boundaries.

The project emphasizes understanding model behavior, generalization capability, and the impact of combining multiple learners to reduce bias and variance.

We evaluate performance across both datasets using a consistent workflow and standardized evaluation metrics.

---

## Dataset
- Wine Dataset

```python
df = pd.read_csv("winequality-red.csv", sep=";")
```
- Spiral Dataset
```python
spiral = pd.read_csv("spiral.csv", sep="\t")
```

---

## Methodology
1. **Data Preparation** – Load datasets, clean if necessary, scale features, and split into training and testing sets.
2. **Baseline Modeling** – Baseline Modeling – Train traditional classifiers for comparison.  
3. **Ensemble Modeling** – Apply multiple ensemble techniques. 
4. **Evaluation** – Compare models using Accuracy and F1-score. 
5. **Analysis** – Interpret results and assess generalization performance using train-test gaps.

---

## Models Evaluated
**Base Models**
   - Logistic Regression
   - K-Nearest Neighbors (KNN)
   - Support Vector Machine (SVM)
   - Decision Tree

**Ensemble Models**
   - Random Forest Classifier
   - Gradient Boosting Classifier
   - AdaBoost Classifier
   - Voting Classifier (Hard Voting)
  All models were evaluated using a shared evaluate_model() function to ensure consistent performance measurement.

---
## Summary Table

| Model Type        | Case   | Configuration                 | Train Accuracy | Test Accuracy | Train F1 | Test F1 | Accuracy Gap | F1 Gap | Notes                                          |
| ----------------- | ------ | ----------------------------- | -------------- | ------------- | -------- | ------- | ------------ | ------ | ---------------------------------------------- |
| Random Forest     | Case 1 | 100 Trees                     | 1.0000         | 0.8875        | 1.0000   | 0.8661  | 0.1125       | 0.1339 | Excellent performance but signs of overfitting |
| Bagging           | Case 2 | Decision Tree, 100 Estimators | 1.0000         | 0.8844        | 1.0000   | 0.8655  | 0.1156       | 0.1345 | Similar to RF, slight overfitting              |
| Random Forest     | Case 3 | 200 Trees, max_depth=10       | 0.9758         | 0.8813        | 0.9745   | 0.8596  | 0.0945       | 0.1148 | Better generalization with controlled depth    |
| Voting Ensemble   | Case 4 | DT + SVM + NN                 | 0.9664         | 0.8719        | 0.9647   | 0.8542  | 0.0945       | 0.1106 | Balanced ensemble performance                  |
| Voting Ensemble   | Case 5 | RF + LR + KNN                 | 0.9187         | 0.8594        | 0.9012   | 0.8280  | 0.0593       | 0.0731 | Lower overfitting, stable model                |
| Gradient Boosting | Case 6 | 100 Estimators                | 0.9601         | 0.8563        | 0.9584   | 0.8411  | 0.1039       | 0.1173 | Good but slightly overfitting                  |
| MLP Classifier    | Case 7 | Default Neural Network        | 0.9711         | 0.8500        | 0.9700   | 0.8458  | 0.1211       | 0.1242 | High variance model                            |
| AdaBoost          | Case 8 | 200 Estimators, lr=0.5        | 0.8038         | 0.7938        | 0.8071   | 0.7938  | 0.0100       | 0.0133 | Most stable but lower accuracy                 |
| AdaBoost          | Case 9 | 100 Estimators                | 0.7834         | 0.7625        | 0.7958   | 0.7743  | 0.0209       | 0.0216 | Underfitting observed                          |

---

## Reflections
**Dataset Insights:**  
- Wine dataset is easier to classify due to structured feature relationships.
- Spiral dataset demonstrates the limitations of linear and simple classifiers.

**Model Insights:**  
- Ensemble models consistently outperform base models across both datasets.
- Random Forest and Gradient Boosting provide robust performance with minimal overfitting.
- Voting Classifier balances predictions but depends on component model quality.

**Observations:**  
- Linear models struggle significantly with non-linear data patterns.
- Ensemble techniques significantly improve decision boundaries.
- Train-test accuracy gap is a strong indicator of overfitting in decision trees.  

---

## Conclusion
This project highlights the effectiveness of ensemble learning in solving complex classification tasks. While base models provide useful benchmarks, ensemble methods offer superior accuracy and stability, particularly for non-linear datasets like Spiral. The study confirms that combining learners leads to better generalization and improved predictive power.
