# SECOM Yield Prediction: A Leakage-Aware Evaluation

Proof-of-concept study on predicting wafer test failures from process
sensor data (UCI SECOM). The focus is on honest evaluation rather than
headline accuracy: time-ordered splits, preprocessing fitted on training
data only, imbalance-aware metrics (PR-AUC, fail-class recall), and a
cost analysis comparing the model against "inspect all" / "inspect none".

Status: work in progress.

## Data
SECOM dataset from the UCI Machine Learning Repository
(https://archive.ics.uci.edu/dataset/179/secom),
by M. McCann and A. Johnston (2008), licensed under CC BY 4.0.
1567 wafers, 590 anonymous sensor features, 104 failures (about 6.6%),
tested between July and October 2008.
The raw files in data/raw/secom/ are unmodified.

Note: features are numbered, not named, so any feature importance result
can only point to "sensor X". In a real fab, the next step would be to
review such findings with process engineers.

## Setup
```bash
python3 -m venv secom-venv
source secom-venv/bin/activate
pip install -r requirements.txt
```

## Project structure
```
data/raw/secom/   original SECOM files
notebooks/        exploration
src/              data loading, splitting, pipelines, evaluation
reports/          figures and results
```
