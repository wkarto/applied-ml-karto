# Project 3 – Titanic Classifier

**Author:** Womenker Karto
**Date:** 2025-11-01  

## Introduction
This project uses the Titanic dataset to build and evaluate three classification models: Decision Tree, Support Vector Machine (SVM), and Neural Network (MLP). The goal is to predict passenger survival based on selected features and compare model performance.  

We explore three feature cases:  
1. **Alone** – whether a passenger was traveling alone.  
2. **Age** – passenger’s age.  
3. **Age + Family Size** – combining age and family members on board.  

A bonus section applies the same process to the Iris dataset for additional practice.

---

## Dataset
The dataset is loaded directly from the `seaborn` library:  

```python
import seaborn as sns
titanic = sns.load_dataset('titanic')
```

Key preprocessing steps included:  
- Filling missing `age` values with median.  
- Filling missing `embark_town` values with mode.  
- Feature engineering: creating `family_size`, mapping `sex` and `embarked` to numeric values, and converting `alone` to numeric.  

---

## Methodology
1. **Data Preparation** – handling missing values and creating numerical features.  
2. **Feature Selection** – selecting one or two features for classification.  
3. **Model Training** – using Decision Tree, SVM (RBF kernel), and Neural Network (MLP).  
4. **Evaluation** – using classification reports, confusion matrices, and visualizations.  
5. **Reflection** – analyzing model performance and insights.  

---

## Summary Table

| Model Type | Case | Features Used | Accuracy | Precision | Recall | F1-Score | Notes |
|------------|------|---------------|----------|-----------|--------|-----------|-------|
| Decision Tree | Case 1 | alone | 62.57% | 51.28% | 57.97% | 54.42% | - |
| Decision Tree | Case 2 | age | 61.45% | 50.00% | 17.39% | 25.81%| - |
| Decision Tree | Case 3 | age+family_size | 59.22% | 46.15% | 34.78%| 39.67% | - |
| SVM (RBF) | Case 1 | alone | 62.57% | 51.28% | 57.97% | 54.42% | - |
| SVM (RBF) | Case 2 | age | 63.13% | 71.43%	 | 7.25% | 13.16% | - |
| SVM (RBF) | Case 3 | age+family_size | 63.13% | 71.43% | 7.25% | 13.16% | - |
| Neural Network | Case 3 | age+family_size | 65.92% | 57.14% | 46.38% | 51.20%| - |


---

## Reflections
**Feature Insights:**  
- `Alone` provides basic social context but limited predictive power.  
- `Age` captures survival bias but has gaps due to missing values.  
- `Family Size + Age` gives the strongest predictive performance.

**Model Insights:**  
- Decision Trees are interpretable and quick to train.  
- SVM works well with complex patterns but may be slower.  
- Neural Networks capture non-linear relationships effectively with two or more features.

**Surprises & Observations:**  
- Case 1 (`alone`) generally performs worse than Cases 2 and 3.  
- Neural Network showed smoother decision boundaries, especially with age + family_size.  
- SVM RBF performed reasonably well without tuning.

---

## Bonus Section
**Iris Dataset Classification**  
- Dataset: Iris (multiclass, 4 numerical features)  
- Models: Decision Tree, SVM, Neural Network  
- Process: same as Titanic – preprocess, split, train, evaluate.  
- Insights: Decision Trees and Neural Networks performed best due to clean numerical features.  

---

## Next Steps / Recommendations
1. Hyperparameter tuning for all models (tree depth, SVM kernel, NN layers).  
2. Feature selection using correlation or feature importance.  
3. Extend analysis to additional datasets (e.g., Breast Cancer, Wine) for more practice.

