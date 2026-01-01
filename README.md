
# Week 3 — Baseline ML System

This repository contains a reproducible baseline machine learning system built during Week 3.
It supports training, evaluation, and batch prediction using a clean CLI and well-defined artifacts.

## Project Overview

- Task type: Binary classification  
- Target:`is_high_value`  
- Model: Logistic Regression (scikit-learn Pipeline)  
- Goal:Provide a reliable, testable ML baseline with clear evaluation artifacts


## Repository Structure
src/                # Core ML code (train, predict, schema, metrics)
tests/              # Pytest unit tests
data/
processed/        # Feature tables
models/
runs/             # All training runs and artifacts
registry/         # Pointer to latest run
reports/
model_card.md     # Model card (filled)
eval_summary.md   # Evaluation summary (filled)
outputs/            # Prediction outputs


## Setup

Create and activate the environment using `uv`:
uv venv
uv pip install -r requirements.txt

## Run the Full Pipeline (Sanity Run)

All commands below are copy/paste runnable

1. Generate sample data

uv run ml-baseline make-sample-data


 2. Train the model

uv run ml-baseline train --target is_high_value


 3. Run batch prediction

```bash
uv run ml-baseline predict \
  --run latest \
  --input data/processed/features.csv \
  --output outputs/preds.csv
```

### 4. Run tests

```bash
uv run pytest
```

After running these steps:

-`outputs/preds.csv` should exist
- A new run folder should exist under `models/runs/`


Model Artifacts

Each training run creates a versioned folder under:

models/runs/<run_id>/


Key artifacts include:

- `metrics/holdout_metrics.json` — evaluation metrics
- `schema/input_schema.json` — inference schema contract
- `tables/holdout_predictions.csv` — predictions with ground truth
- `run_meta.json` — full run metadata
-`env/pip_freeze.txt` — environment snapshot

The file below always points to the most recent run:
models/registry/latest.txt


## Reports

Model Card: `reports/model_card.md`
Evaluation Summary:`reports/eval_summary.md`

Both reports are filled using real results from the latest run.



## What you submit

- working code (`src/`)
- passing tests (`tests/`)
- filled `reports/model_card.md`
- filled `reports/eval_summary.md`





