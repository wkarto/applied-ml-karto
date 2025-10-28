# Project 02 — Titanic Dataset Analysis

## Overview
This project analyzes the **Titanic dataset** using the same process demonstrated in **Lab 2**. It focuses on data exploration, preparation, feature engineering, and splitting for model training. The notebook follows a clearly structured and reflective approach to reinforce analytical thinking.

## Objectives
1. Import and inspect the dataset.
2. Explore data patterns and handle missing values.
3. Engineer features that improve predictive capability.
4. Select meaningful features and justify their use.
5. Split the dataset into training and testing subsets (both random and stratified splits).
6. Reflect after each major section to strengthen understanding.
7. Apply the same process on an additional dataset for bonus credit.

## Files and Folder Structure
```
notebooks/
  └── project02/
        ├── ml02_karto.ipynb
        ├── README.md
```

## Dependencies
This project uses the same external dependencies as **Project 1**:

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

Install all dependencies using pip if needed:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Dataset
The Titanic dataset is loaded directly from **seaborn**:
```python
import seaborn as sns
titanic = sns.load_dataset('titanic')
```

This dataset includes passenger demographics, class, fare, and survival information from the RMS Titanic tragedy.

## Notebook Sections
| Section | Description |
|----------|--------------|
| **1. Import and Inspect the Data** | Load, inspect, and understand data structure and quality. |
| **2. Data Exploration and Preparation** | Visualize, clean, and engineer new features. |
| **3. Feature Selection and Justification** | Choose meaningful variables for prediction. |
| **4. Splitting** | Compare basic and stratified train/test splits. |
| **Bonus** | Apply the same analytical process to the Iris dataset. |

## Reflections
Each section concludes with reflection questions that encourage critical thinking and documentation of insights.

## Bonus Work
For additional credit, the same EDA and preparation process is applied to the **Iris dataset**, demonstrating adaptability of the pipeline across datasets.

## How to Run
1. Open the repository folder in VS Code.
2. Navigate to `notebooks/project02/`.
3. Open `ml02_karto.ipynb` in Jupyter or VS Code.
4. Run all cells sequentially to reproduce results.

## Author
**Name:** Womenker Karto  
**Date:** October 28, 2025  
**Course:** Project 02 — Data Features (Titanic)
---


