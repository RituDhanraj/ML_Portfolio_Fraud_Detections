# Model Card — Credit Card Fraud Detection

## Model Details
- **Model Type:** RandomForestClassifier (primary), Logistic Regression (baseline)
- **Version:** v0.1 (starter)
- **Authors:** Your Name
- **Frameworks:** scikit-learn
- **Training Data:** Kaggle Credit Card Fraud Detection (`creditcard.csv`)

## Intended Use
- **Primary use:** Educational portfolio demonstrating ML workflow and Bayesian Optimization.
- **Out-of-scope:** High-stakes decisions without rigorous validation, monitoring, and governance.

## Factors
- **Input features:** PCA-transformed components V1–V28 plus `Amount` (from dataset).
- **Sensitive attributes:** Not explicitly included; dataset is anonymized.
- **Class imbalance:** Highly imbalanced; fraud is rare.

## Metrics
- **Primary:** ROC-AUC, PR AUC
- **Secondary:** Precision, Recall, F1, confusion matrix

## Evaluation Data
- Stratified train/validation/test splits from the original dataset.

## Ethical Considerations
- Risk of false positives (customer friction) and false negatives (fraud losses).
- Document thresholds, monitor drift, and review false positive/negative cases.

## Caveats & Recommendations
- This is a demo. Do not deploy without calibration, threshold analysis, and monitoring.
- Consider cost-sensitive learning or custom decision thresholds.
