# Machine Learning Portfolio Project – Credit Card Fraud Detection

This repository showcases a complete ML project using the **Kaggle Credit Card Fraud Detection** dataset (European card transactions, 2013).
It demonstrates end-to-end workflow: data handling, model training, **Bayesian Optimization** for hyperparameter tuning, documentation (**Model Card** and **Datasheet**), and reproducible results.

> **Dataset:** Kaggle – *Credit Card Fraud Detection* (search on Kaggle and download `creditcard.csv`).  
> **Place file here:** `data/raw/creditcard.csv` (excluded from git by default).

## 🔍 Project Goals
- Predict whether a transaction is fraudulent (binary classification, extreme class imbalance).
- Compare baseline vs tuned models.
- Document the dataset and model decisions transparently.

## 📁 Repository Structure
```
.
├── data/
│   ├── raw/                # Put original datasets here (e.g., creditcard.csv)
│   └── processed/          # Saved clean/feature-engineered data (generated)
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_model_training.ipynb
│   ├── 03_hyperparameter_tuning.ipynb
│   └── 04_results_and_visualizations.ipynb
├── models/                 # Saved trained models (optional)
├── docs/
│   ├── model_card.md
│   └── datasheet.md
├── requirements.txt
├── .gitignore
└── README.md
```

## 🧠 Methods Overview
- **Models:** Logistic Regression, Random Forest (primary), and Gradient Boosting (optional).
- **Hyperparameter Tuning:** `bayes_opt` (Bayesian Optimization) over continuous/discrete spaces.
- **Metrics:** ROC-AUC (primary), Precision/Recall, F1, and PR AUC (recommended for imbalance).

## 🧰 Environment
```
pip install -r requirements.txt
```

## 🚀 How to Run (local)
1. Download `creditcard.csv` from Kaggle and place it in `data/raw/`.
2. Open the notebooks in order inside `notebooks/`:
   - `01_data_exploration.ipynb`
   - `02_model_training.ipynb`
   - `03_hyperparameter_tuning.ipynb`
   - `04_results_and_visualizations.ipynb`
3. (Optional) Save trained model artifacts into `models/`.

## 📝 Documentation
- **Model Card:** `docs/model_card.md`
- **Dataset Datasheet:** `docs/datasheet.md`

## 🏷 License
This repository is provided for educational portfolio purposes. You are responsible for complying with the dataset license on Kaggle.

— Generated starter on 2025-10-16
