# applied-ml-karto

---

## About this Repository

This repository contains the starter files and setup for the Applied Machine Learning project.  
For this week, the task was to **set up the local environment and successfully run the example machine learning notebook** (`ml01.ipynb`) as required.

---

## Completed Work for This Week

Verified environment setup using `uv`.  
Activated virtual environment.  
Installed required dependencies using:

```bash
uv sync --extra dev --extra docs --upgrade
```

Successfully ran the example notebook:

```bash
uv run python notebooks/project01/ml01.py
```

Confirmed that the ML model (Linear Regression on the California Housing dataset) executed successfully and generated expected charts and outputs.

---

## Next Steps

- Begin exploring a new dataset from Kaggle.  
- Apply similar workflow to train and evaluate your own regression or classification model.  
- Update this README in the next milestone with project-specific details.  

---

## Commands Used

To prepare and execute the project environment:

```bash
uv venv
uv python pin 3.12
uv sync --extra dev --extra docs --upgrade
uv run pre-commit install
```

Activate the environment:

- **Windows (PowerShell):**
  ```bash
  .\.venv\Scripts\activate
  ```
- **macOS / Linux / WSL:**
  ```bash
  source .venv/bin/activate
  ```

Then, run the project:

```bash
uv run python notebooks/project01/ml01.ipynb
```

---

## Notes

- The project demonstrates a **Linear Regression** model using the **California Housing dataset** from `sklearn.datasets`.  
- The notebook performs train/test split, model training, prediction, and evaluation using metrics such as **MAE**, **MSE**, and **R²**.  
- Visualizations (histograms, scatter plots) were generated to explore relationships between features and target variables.  

---