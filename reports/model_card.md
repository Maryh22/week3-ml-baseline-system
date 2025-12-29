# Model Card — Week 3 ML Baseline

## 1. Model Purpose
This model predicts whether a user is a high-value user based on their historical order behavior.

**Target (y):**
- `is_high_value` (binary: 0 or 1)

**Unit of analysis:**
- One row per user

---

## 2. Input Data (Dataset Contract)

### ID Columns (passthrough)
- `user_id`

### Feature Columns (X)
- `country`
- `n_orders`
- `avg_amount`
- `total_amount`

### Target Column (y)
- `is_high_value`

### Forbidden Columns
- `is_high_value` must never be used as a feature during training or inference.

---

## 3. Data Source
Sample feature table generated using `ml-baseline make-sample-data`.

---

## 4. Evaluation Plan
- Train / validation split
- Primary metric: ROC AUC
- Secondary metrics: accuracy, precision, recall

---

## 5. Limitations
- Sample data is synthetic and small.
- Performance metrics may not generalize to real-world data.
