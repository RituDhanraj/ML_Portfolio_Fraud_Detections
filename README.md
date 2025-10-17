# Machine Learning Portfolio Project – Credit Card Fraud Detection

## Non-technical summary (≈100 words)
This project detects potentially fraudulent card transactions. We trained a machine-learning model on an anonymised public dataset and tuned it to balance “catching fraud” with “avoiding false alarms.” The model first explores patterns in the data, then learns to rank transactions by risk. On our test set it achieved strong ranking performance (ROC-AUC 0.974; PR-AUC 0.756). Because teams act on alerts, we chose a practical decision threshold (0.82) to reduce false positives while keeping a high catch rate (Precision ≈ 0.50, Recall ≈ 0.83). Results, documentation, and how to reproduce them are provided so others can review and reuse this work.

---

## Results
**Dataset:** Kaggle — Credit Card Fraud Detection  
**Model:** Random Forest (tuned with Bayesian Optimization)

- ROC–AUC: **0.9738**  
- PR–AUC: **0.7557**  
- Operating threshold: **0.82**  
  - Precision **0.503**, Recall **0.827**, F1 **0.626**  
  - Confusion matrix: **TN=56,784, FP=80, FN=17, TP=81**

**Why this threshold?** Highest recall subject to **precision ≥ 0.50** to cut false-positive reviews while catching most fraud.

📄 Artifact: [models/fraud_rf_artifact.json](models/fraud_rf_artifact.json)  
📈 PR curve:  
![Precision–Recall curve](docs/pr_curve.png)  
👀 View final notebook (nbviewer):  
[https://nbviewer.org/github/RituDhanraj/ML_Portfolio_Fraud_Detections/blob/main/notebooks/04_results_and_visualizations.ipynb](https://colab.research.google.com/github/RituDhanraj/ML_Portfolio_Fraud_Detections/blob/main/notebooks/04_results_and_visualizations.ipynb)

---

## Data
Source: Kaggle — Credit Card Fraud Detection  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

- Download **`creditcard.csv`** and place it at **`data/raw/creditcard.csv`**.  
- Large datasets are **linked** rather than stored in this repo. See [`docs/datasheet.md`](docs/datasheet.md).

---

## Reproduce the results

```bash
# create & activate environment
python -m venv venv
venv\Scripts\activate   # mac/linux: source venv/bin/activate

# install dependencies
pip install -r requirements.txt
Run notebooks in order:

notebooks/01_data_exploration.ipynb

notebooks/02_model_training.ipynb

notebooks/03_hyperparameter_tuning.ipynb

notebooks/04_results_and_visualizations.ipynb (saves docs/pr_curve.png and reports final metrics)

Artifacts:

Parameters + threshold saved to: models/fraud_rf_artifact.json

(Optional) Trained model: models/fraud_rf.pkl (git-ignored)

Repository structure
bash
Copy code
.
├── data/
│   ├── raw/                # Put original dataset here (creditcard.csv)
│   └── processed/          # Generated data (optional, git-ignored)
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_model_training.ipynb
│   ├── 03_hyperparameter_tuning.ipynb
│   └── 04_results_and_visualizations.ipynb
├── models/                 # Artifacts (JSON tracked; binaries git-ignored)
├── docs/
│   ├── model_card.md
│   ├── datasheet.md
│   └── pr_curve.png
├── requirements.txt
├── .gitignore
└── README.md
Methods overview
Models: Logistic Regression, Random Forest (primary), (optional) Gradient Boosting

Hyperparameter tuning: bayes_opt (Bayesian Optimization)

Metrics: ROC–AUC, Precision/Recall, F1, PR–AUC (recommended for imbalance)

Thresholding: choose operating point to maximize recall with precision ≥ 0.50

Environment
bash
Copy code
pip install -r requirements.txt
Documentation
Model Card: docs/model_card.md

Dataset Datasheet: docs/datasheet.md

License
This repository is provided for educational portfolio purposes. You are responsible for complying with the dataset license on Kaggle.

yaml
Copy code

---

### Why replace everything?
Your current README has all the right info but it’s in plain text; the version above fixes headings, bullets, code blocks, links, and embeds the PR curve image so markers can scan it quickly.

If anything doesn’t render (e.g., the image), it means that file isn’t in the repo yet—upload it to the path shown and it will work immediately.

— Generated starter on 2025-10-16
