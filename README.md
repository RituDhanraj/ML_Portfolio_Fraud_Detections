# Machine Learning Portfolio Project – Credit Card Fraud Detection
A) Non-technical write-up (≈100 words)
This project detects potentially fraudulent card transactions. We trained a machine-learning model on an anonymised public dataset and tuned it to balance “catching fraud” with “avoiding false alarms.” The model first explores patterns in the data, then learns to rank transactions by risk. On our test set it achieved strong ranking performance (ROC-AUC 0.974; PR-AUC 0.756). Because teams act on alerts, we chose a practical decision threshold (0.82) to reduce false positives while keeping a high catch rate (Precision ≈ 0.50, Recall ≈ 0.83). Results, documentation, and how to reproduce them are provided so others can review and reuse this work.

This repository showcases a complete ML project using the **Kaggle Credit Card Fraud Detection** dataset (European card transactions, 2013).
It demonstrates end-to-end workflow: data handling, model training, **Bayesian Optimization** for hyperparameter tuning, documentation (**Model Card** and **Datasheet**), and reproducible results.

> **Dataset:** Kaggle – *Credit Card Fraud Detection* (search on Kaggle and download `creditcard.csv`).
>
> B) Results (with links to artifacts + notebook)
> **Dataset:** Kaggle — Credit Card Fraud Detection  
**Model:** Random Forest (tuned with Bayesian Optimization)

- ROC–AUC: **0.9738**
- PR–AUC: **0.7557**
- Operating threshold: **0.82**
  - Precision **0.503**, Recall **0.827**, F1 **0.626**
  - Confusion matrix: TN=56,784, FP=80, FN=17, TP=81

**Why this threshold?** Highest recall subject to **precision ≥ 0.50** to cut false-positive reviews while catching most fraud.

📄 Artifact: [models/fraud_rf_artifact.json](models/fraud_rf_artifact.json)  
📈 PR curve: ![Precision–Recall curve](docs/pr_curve.png)  
👀 View final notebook (nbviewer): https://nbviewer.org/github/RituDhanraj/ML_Portfolio_Fraud_Detections/blob/main/notebooks/04_results_and_visualizations.ipynb?flush=1

>C) Data + Reproduce
>
> ## Data
Source: Kaggle — Credit Card Fraud Detection  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Download `creditcard.csv` and place it at `data/raw/creditcard.csv`.  
Large datasets are linked rather than stored in this repo. See `docs/datasheet.md`.

## Reproduce the results
```bash
python -m venv venv
venv\Scripts\activate   # mac/linux: source venv/bin/activate
pip install -r requirements.txt


> **Place file here:** `data/raw/creditcard.csv` (excluded from git by default).

Run notebooks in order:

notebooks/01_data_exploration.ipynb

notebooks/02_model_training.ipynb

notebooks/03_hyperparameter_tuning.ipynb

notebooks/04_results_and_visualizations.ipynb (saves docs/pr_curve.png, reports final metrics)

### 5) Datasheet & Model Card (Module 20 requirement)
Open **`docs/datasheet.md`** and **`docs/model_card.md`** and ensure they state:
- Datasheet: Kaggle URL, access date, features (V1–V28, Time, Amount), label (Class), stratified 80/20 split, class imbalance, anonymisation limits.
- Model card: intended use (analyst triage), out-of-scope (fully automated decisions), **operating threshold 0.82** with metrics, ethical considerations (FP cost, customer friction, drift monitoring).

### 6) Ignore virtual env & raw data
- `.gitignore` must include:

venv/
data/raw/*
data/processed/*
models/*
!models/*.json

- If `venv/` is in the repo, delete it (locally → Commit → Push, or on the web by removing its contents), then add `venv/` to `.gitignore`.

### 7) “Website” link in About (nice touch)
Set to your nbviewer link:  
`https://nbviewer.org/github/RituDhanraj/ML_Portfolio_Fraud_Detections/blob/main/notebooks/04_results_and_visualizations.ipynb?flush=1`

---

## 🔎 60-second self-audit before you submit
- Can I open **notebooks/04_results_and_visualizations.ipynb** on GitHub?  
- Does the **nbviewer link** render the notebook?  
- Does the README show the **PR curve image** and the **Results** numbers?  
- Do **model_card.md** and **datasheet.md** exist and look filled?  
- Is there **no `venv/`** and **no `creditcard.csv`** in the repo?  
- Is the repo **Public**?

If anything is missing, upload that single file via **Add file → Upload files** into the right folder, **Commit changes**, refresh.

---

### ✅ Submit
Paste this in your submission field:  
`https://github.com/RituDhanraj/ML_Portfolio_Fraud_Detections`

If you want me to eyeball the repo structure once more (what’s showing in each folder), tell me what’s currently visible on the GitHub page and I’ll call out any final fixes.


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
