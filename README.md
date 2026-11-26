# Cancer Prediction Project

This repository contains Jupyter notebooks exploring machine-learning classification on several public health datasets. The notebooks cover data cleaning, exploratory visualizations, model training, and evaluation. They are separate experiments, not one integrated application.

> **Important:** These notebooks are for learning and research only. They are not medical devices and must not be used to diagnose, screen, or guide treatment. Predictions are not clinically validated.

## Notebooks

| Notebook | What it explores |
| --- | --- |
| `breast_cancer_ML.ipynb` | Breast cancer classification with CatBoost using the Wisconsin Original dataset. |
| `heart_disease_ML.ipynb` | Heart disease classification with CatBoost and XGBoost using the Cleveland heart-disease dataset. |
| `HCC_cancer_ML.ipynb` | Hepatitis C dataset classification, including preprocessing, model comparisons, ensemble experiments, and feature-importance analysis. The notebook filename says HCC, but its input is `HepatitisCdata.csv`. |
| `ovarien_cancer.ipynb` | Ovarian cancer dataset exploration and Random Forest/XGBoost experiments. |
| `panceatic_cancer_ML.ipynb` | Pancreatic cancer dataset exploration and Random Forest classification experiments. |

The notebooks use train/test splits and, in some experiments, cross-validation and grid search. Metrics and plots are produced by individual notebooks; results may vary with dataset versions and execution environment.

## Data

The datasets are **not included** in this repository. Obtain each dataset from its original source, check its license and citation requirements, and place it somewhere on your computer:

| Notebook | Expected input file |
| --- | --- |
| Breast cancer | `breast-cancer-wisconsin.data` |
| Heart disease | `processed.cleveland.data` |
| Hepatitis C | `HepatitisCdata.csv` |
| Ovarian cancer | `Supplementary data 3(Imputed training data without C).csv` |
| Pancreatic cancer | `Debernardi et al 2020 data.csv` |

The notebooks currently contain absolute file paths from another computer. Before running a notebook, edit its `pd.read_csv(...)` path(s) to point to the dataset file on your machine. For a more portable setup, you can put the files in a local `data/` directory and use paths such as `data/HepatitisCdata.csv`. Do not commit datasets unless you have permission to redistribute them.

## Setup

Use Python 3.10 or later. From the project directory, create and activate a virtual environment.

**Windows PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
python -m venv .venv
source .venv/bin/activate
```

Install the libraries used by the notebooks and start JupyterLab:

```bash
python -m pip install --upgrade pip
python -m pip install jupyterlab pandas numpy scikit-learn catboost xgboost imbalanced-learn matplotlib seaborn shap
jupyter lab
```

Open a notebook in JupyterLab, update its data paths, and run its cells from top to bottom. Some notebooks contain multiple alternative experiments; run the cells relevant to the experiment you want.

## Notes and limitations

- There is no shared Python package, command-line interface, web application, or saved model in this repository; the notebooks are the project deliverables.
- Experiments use different preprocessing and evaluation choices, so their scores should not be compared as if they came from one standardized benchmark.
- Some cells are exploratory and may need adjustment to run in a fresh environment. In particular, the pancreatic notebook's SHAP cell refers to a variable named `model`; make sure it refers to the estimator you have fitted before running that cell.
- High test or cross-validation scores on these datasets do not establish clinical usefulness, generalization to new populations, or suitability for patient care.
