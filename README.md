# Electrical Supply Line Distortion Detection Using ML Models

A machine learning project that detects and classifies faults in three-phase electrical power supply lines using current and voltage measurements.

## Problem Statement

Faults in electrical supply lines can cause equipment damage, power outages, and safety hazards. This project aims to automatically detect and classify the type of fault occurring in a three-phase power system using machine learning, enabling faster and more reliable fault response.

## Dataset

- **Features:** Current and voltage readings for all three phases — `Ia`, `Ib`, `Ic`, `Va`, `Vb`, `Vc`
- **Labels:** Binary columns `A`, `B`, `C`, `G` indicating fault status of each line and ground
- **Fault Types Classified:**

| Code | Fault Type |
|------|-----------|
| 0000 | NO Fault |
| 1001 | Line A to Ground Fault |
| 0110 | Line B to Line C Fault |
| 1011 | Line A Line B to Ground Fault |
| 0111 | Line A Line B Line C Fault |
| 1111 | Line A Line B Line C to Ground Fault |

## Project Workflow

1. **Data Loading** — Load current and voltage readings for all three phases
2. **Feature Engineering** — Combine A, B, C, G columns into a single `Fault_Type` column
3. **Data Analysis** — Visualize fault distributions using count plots
4. **Graphical Analysis** — Plot current and voltage waveforms for each fault type
5. **Label Encoding** — Convert fault type strings to numerical labels
6. **Train/Test Split** — 80/20 split with `random_state=21`
7. **Model Training** — Train and evaluate multiple ML classifiers
8. **Model Comparison** — Compare accuracy scores across all models

## Models Used

| Model | Description |
|-------|-------------|
| Random Forest | Ensemble of decision trees |
| Decision Tree | Single tree classifier |
| XGBoost | Gradient boosted trees |
| Support Vector Machine (SVM) | Kernel-based classifier |
| Logistic Regression | Linear probabilistic classifier |

## Results

Best performing models were **Random Forest**, **XGBoost**, and **Decision Tree**, all achieving high accuracy on the test set. Logistic Regression and SVM performed comparatively lower due to the non-linear nature of the fault patterns.


## setup
### 2. Create and activate virtual environment
```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

### 3. Install dependencies
```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost jinja2 ipykernel
```

### 4. Register the kernel (for Jupyter)
```bash
python -m ipykernel install --user --name=.venv --display-name "Python (.venv)"
```

### 5. Run the notebook
Open `main.ipynb` in VS Code or Jupyter and select the **"Python (.venv)"** kernel, then run all cells.


## Dependencies

- Python 3.12
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- jinja2
- ipykernel
