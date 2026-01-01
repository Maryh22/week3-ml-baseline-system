# Model Card — Week 3 Baseline

## Problem
- Target: `is_high_value`
- Unit of analysis: user (one row per user)
- Decision enabled: Predict whether a user is high value (1) or not (0) to support downstream business decisions (e.g. targeting or prioritization).

## Data
- Feature table: `data/processed/features.csv`
- Dataset hash (sha256):  
  `6bda418ff35552e80ee9f66ce1a24c434e51ac59d69d0ff099c68ea623456ebe`

## Splits
- Holdout: random split  
- Test size: 0.2  
- Seed: 42  
- Strategy: random stratified split

## Metrics (holdout)
- Baseline:
  - ROC AUC: 0.50  
  - PR AUC: 0.20  
  - Accuracy: 0.80  
- Model (Logistic Regression):
  - ROC AUC: 1.00  
  - PR AUC: 1.00  
  - Accuracy: 1.00  
  - Precision: 1.00  
  - Recall: 1.00  
  - F1-score: 1.00  

## Limitations
- Dataset is small, which may lead to overly optimistic metrics.
- Perfect holdout performance suggests potential data simplicity or leakage risk.
- Features are limited and may not generalize well to real-world data.

## Monitoring sketch
- Monitor prediction positive rate over time.
- Track feature distribution drift (e.g. country, avg_amount).
- Recompute holdout metrics periodically after retraining.

## Reproducibility
- Run id: `2025-12-30T20-43-06Z__classification__seed42`
- Git commit: `<PASTE git commit hash here>`
- Env: `models/runs/2025-12-30T20-43-06Z__classification__seed42/env/pip_freeze.txt`
