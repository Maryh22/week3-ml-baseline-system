# Evaluation Summary — Week 3

## What you trained
- Model family:
  LogisticRegression (binary classification)
- Preprocessing:
  - Numerical features: median imputation
  - Categorical features: most-frequent imputation + one-hot encoding
  - Implemented using a scikit-learn Pipeline
- Key hyperparameters:
  - max_iter = 500
  - decision threshold = 0.5
  - random seed = 42

## Results
- Baseline metrics:
  - DummyClassifier (majority class) achieved an accuracy of 0.80 on the holdout split.
  - ROC-AUC = 0.50, PR-AUC = 0.20.
- Holdout metrics:
  - LogisticRegression pipeline achieved perfect performance on the holdout split:
    - Accuracy = 1.00
    - Precision = 1.00
    - Recall = 1.00
    - F1-score = 1.00
    - ROC-AUC = 1.00 (95% CI: [1.00, 1.00])
  - Positive class rate in the holdout data was 0.20.
- Confidence intervals (optional):
  - ROC-AUC 95% CI: [1.00, 1.00]

## Error analysis
- Worst cases:
  - No clear misclassifications were observed in the holdout set due to the small, synthetic dataset.
- Any obvious leakage?
  - No target leakage was detected; inference explicitly rejects inputs containing the target column (`is_high_value`).
- Next data fixes to try:
  - Evaluate the model on a larger, real-world dataset.
  - Add more challenging edge cases and class imbalance.
  - Analyze performance across data slices (e.g., country).

## Recommendation
Yes, ship as a technical baseline only.
The model clearly outperforms the baseline and the pipeline is reproducible.
However, results should be interpreted with caution due to the small, synthetic dataset used for evaluation.

## Run ID
2026-01-01T14-57-01Z__classification__seed42
