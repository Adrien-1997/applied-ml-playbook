# Applied ML Playbook

Opinionated, reproducible notebooks for common DS problems — **statistics first**, strong baselines, and clear evaluation.

---

## What’s inside
- **EDA patterns:** robust summaries, leakage checks, target drift  
- **Supervised baselines:** linear/logistic, tree-based, calibration  
- **Anomaly detection:** IsolationForest with ROC + business costs  
- **Time series:** stationarity, ARIMA/VAR/GARCH (light), cross-validation  
- **Evaluation:** ROC/PR, Precision@K, cost matrices, confidence intervals  
- **Visualization:** high-signal plots that communicate decisions

---

## Structure (suggested)
~~~text
.
├─ notebooks/
│  ├─ 01_eda_basics.ipynb
│  ├─ 02_supervised_baselines.ipynb
│  ├─ 03_anomaly_iforest_thresholding.ipynb
│  ├─ 04_time_series_basics_arima_var_garch.ipynb
│  └─ 05_evaluation_roc_pr_costs.ipynb
├─ src/                     # small reusable helpers
│  ├─ io.py
│  ├─ metrics.py
│  └─ viz.py
├─ data/
│  └─ README.md             # documented sources only (no data)
├─ assets/                  # figures for README
├─ requirements.txt
├─ .gitignore
├─ LICENSE
└─ README.md
~~~

---

## Reproduce
~~~bash
python -m venv .venv
# activate venv...
pip install -r requirements.txt
jupyter notebook
~~~

---

## Principles
- **Statistics first:** start simple, quantify uncertainty  
- **One metric that matters:** define success before modeling  
- **Reproducibility:** deterministic seeds, pinned deps, clean notebooks

---

## License
**MIT**

---

### Appendix — Minimal `requirements.txt`
~~~text
jupyter
numpy
pandas
scikit-learn
matplotlib
plotly
statsmodels
~~~

### Appendix — Minimal `.gitignore`
~~~gitignore
.venv/
__pycache__/
.ipynb_checkpoints/
data/*
!data/README.md
~~~
3) kaggle-learning/README.md
yaml
Copier le code
# Kaggle — Learning in Public

Clean, reproducible notebooks organized **by competition**, with metrics, validation, and takeaways.  
This repo documents *process* as much as *score*.

---

## Repository layout
~~~text
.
├─ competitions/
│  ├─ titanic/
│  │  ├─ 01_eda.ipynb
│  │  ├─ 02_baseline.ipynb
│  │  ├─ 03_feature_engineering.ipynb
│  │  ├─ 04_modeling.ipynb
│  │  └─ README.md        # objective → metric → best LB → lessons
│  ├─ house-prices/
│  │  ├─ ...
│  └─ ...
├─ tools/
│  └─ kaggle_helpers.py   # CV, scoring, plots
├─ assets/
│  └─ preview.png
├─ requirements.txt
├─ .gitignore
└─ LICENSE
~~~

---

## Suggested README per competition
~~~markdown
# [Competition Name]

**Objective**: (what to predict)  
**Metric**: (e.g., RMSLE / AUC)  
**Best public LB**: X.XXXX (date)  
**Approach**:
- Baseline: [model + features]
- Improvements: [what moved the metric]
- Validation: [CV scheme, leakage checks]

**Key takeaways**
1) …
2) …
3) …

**Reproduce**
- Install deps: `pip install -r ../../requirements.txt`
- Run notebook(s) in order
- Submit with: [...]
~~~

---

## Reproduce (global)
~~~bash
python -m venv .venv
# activate venv...
pip install -r requirements.txt
jupyter notebook
~~~

---

## Principles
- **Organized by challenge**, not by date  
- **Document validation:** CV must mirror LB metric  
- **Keep only winning changes:** clean final notebooks

---

## License
**MIT**

---

### Appendix — Minimal `requirements.txt`
~~~text
jupyter
numpy
pandas
scikit-learn
matplotlib
xgboost
lightgbm
~~~

### Appendix — Minimal `.gitignore`
~~~gitignore
.venv/
__pycache__/
.ipynb_checkpoints/
.kaggle/
competitions/*/input/
competitions/*/working/
~~~
