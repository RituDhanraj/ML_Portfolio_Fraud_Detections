# Dataset Datasheet — Kaggle Credit Card Fraud Detection

## Motivation
- **Dataset Creator:** ULB Machine Learning Group.
- **Composition:** European credit card transactions (2013), anonymized via PCA.
- **Task:** Binary classification (fraud vs non-fraud).

## Data Collection & Processing
- Features V1–V28 are PCA components; `Amount` is transaction amount; `Time` is time elapsed.
- Labels: `Class` (1 = fraud, 0 = legitimate).

## Uses
- Fraud detection research, classification algorithms, imbalanced learning.

## Distribution
- Available on Kaggle as `creditcard.csv`. Check Kaggle license/terms before use.

## Maintenance
- No updates expected. Treat as a static dataset.
