# Midterm Project: Classification Analysis — Titanic Survival Prediction

**Author:** Womenker KArto 
**Date:** 2025-11-10

---

## Overview

This project applies **classification modeling** to predict **Titanic passenger survival** using the classic **Kaggle Titanic Dataset**.  
The goal is to understand how passenger characteristics influenced survival outcomes and to compare two classifiers: **Logistic Regression** and **Random Forest**.

This notebook demonstrates:
- Data exploration and preprocessing  
- Feature selection and encoding  
- Model training and evaluation  
- Model comparison and reflection  

---

## Dataset Information

**Dataset:** Titanic 
**Target Variable:** `Survived` (1 = Survived, 0 = Did not survive)

**Selected Features:**
- `Pclass` — Passenger class (1, 2, 3)  
- `Sex` — Gender of passenger  
- `Age` — Age of passenger  
- `SibSp` — Number of siblings/spouses aboard  
- `Parch` — Number of parents/children aboard  
- `Fare` — Passenger fare  
- `Embarked` — Port of embarkation  

**Objective:** Predict whether a passenger survived based on these features.

---

## Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/wkarto/applied-ml-karto.git
cd midterm
```

### 2. Create and Activate Virtual Environment
```bash
python -m venv venv
source venv/bin/activate        # For macOS/Linux
venv\Scripts\activate           # For Windows
```

### 3. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 4. Run the Notebook

Open midterm_project_karto.ipynb and run all cells in order.

---

## Results Summary

### Logistic Regression Metrics
- **Accuracy:** 0.771  
- **Precision:** 0.716  
- **Recall:** 0.674  
- **F1-score:** 0.695  
- **ROC AUC:** 0.836  

**Confusion Matrix:**
[[114 23]
[ 28 58]]

---

### Random Forest Metrics
- **Accuracy:** 0.771  
- **Precision:** 0.733  
- **Recall:** 0.640  
- **F1-score:** 0.683  
- **ROC AUC:** 0.829  

**Confusion Matrix:**
[[117 20]
[ 31 55]]

---

### Comparison Summary
- Logistic Regression F1-score: 0.695  
- Random Forest F1-score: 0.683  
- Logistic Regression ROC AUC: 0.836  
- Random Forest ROC AUC: 0.829  

**Insight:** Logistic Regression slightly outperforms Random Forest in F1 and ROC AUC, while both have equal accuracy.

---

## Reflections Summary

### Reflection 1
The Titanic dataset contains passenger demographics, ticket details, and survival outcomes. Some columns like **Age** and **Cabin** have missing values which were handled via median imputation.

### Reflection 2
Features such as **Sex**, **Pclass**, and **Fare** showed clear patterns. Survival rates were higher for females and higher-class passengers. Outliers in **Fare** were handled by capping.

### Reflection 3
Selected features: **Pclass**, **Sex**, **Age**, **Fare**, **Embarked**.  
These are influential for predicting survival. Categorical variables were encoded numerically.  

### Reflection 4
Logistic Regression achieved **77% accuracy**. Gender and passenger class were strong predictors. No major surprises observed.

### Reflection 5
Both models performed similarly, but **Logistic Regression** slightly outperformed Random Forest in **F1** and **ROC AUC**.  
It is simpler and more interpretable, making it the preferred choice for this dataset.

### Reflection 6
The project reinforced concepts of **data preprocessing**, **feature engineering**, and **model evaluation**.  
Future improvements could include hyperparameter tuning, feature interactions, or Gradient Boosting models for better accuracy.

---

## Links
- [Notebook](./midterm/midterm_project_karto.ipynb)  
- [Peer Review - peer_review.md](./midterm/peer_review.md)

---
