# Konstantin Grigorchak

**ML Engineer / Data Scientist**

I build machine-learning solutions around tabular data, model validation, optimization and applied engineering. I care about reproducible experiments, reliable validation and understanding **where model improvements actually come from** — not just trying more algorithms.

My main stack is Python, PyTorch and the classical ML ecosystem. Most of my public ML work is collected in [`ml-projects`](https://github.com/GriGkos/ml-projects).

---

## Selected projects

### Home Credit Default Risk

**Credit-risk scoring using current application data and detailed customer credit history.**  
`CatBoost` · `LightGBM` · `PyTorch` · `Optuna` · `SHAP` · `Permutation Importance`

- **OOF ROC-AUC:** `0.79405`
- **Kaggle Private:** `0.79510`
- final feature matrix: **2,708 features**
- compared Logistic Regression, Decision Tree, LightGBM, CatBoost and MLP on the same 5-fold OOF scheme
- measured the contribution of historical data separately from the contribution of model complexity
- used cross-fitted blending, calibration analysis, SHAP, grouped permutation importance, FP/FN analysis and fairness diagnostics

The detailed credit history improved LightGBM by **+0.01814 ROC-AUC** over the application-only setup. A cross-fitted CatBoost + LightGBM blend slightly improved OOF, but did not improve the hidden Kaggle leaderboard, so CatBoost remained the final model.

[Open project](https://github.com/GriGkos/ml-projects/tree/main/projects/04_home_credit_scoring)

---

### Elo Merchant Category Recommendation

**Customer-loyalty regression from large-scale transaction history.**  
`XGBoost` · `LightGBM` · `CatBoost` · `Optuna` · `Target Encoding` · `Bootstrap`

- processed more than **29 million historical transactions**
- built card-level aggregates from large tables using chunked processing
- compared LightGBM, XGBoost and CatBoost with Optuna tuning
- implemented fold-safe target encoding, seed bagging, weighted blending and stacking
- checked whether a tiny ensemble gain was statistically meaningful with paired bootstrap

**Kaggle Private RMSE:** `3.60826`  
**Private leaderboard:** **82 / 4,111 — Top 1.99%**

The more complex stacking solution had the best raw OOF score, but its advantage over XGBoost seed bagging was not statistically stable. I kept the simpler solution for the final submission.

[Open project](https://github.com/GriGkos/ml-projects/tree/main/projects/03_elo_merchant)

---

### Gas Pipeline Balancer

**Python replacement for an Excel/VBA workflow used to balance gas pipeline systems.**  
`Python` · `Numerical Methods` · `Xlwings` · `Excel Automation`

- replaced a rigid VBA macro with a cross-platform Python tool
- processes coefficient ranges instead of calculating values one by one
- uses Newton's method for faster convergence
- supports several calculation modes and configurable subsystem priorities
- integrates with existing Excel-based workflows

**Computation time:** `40–50 min → 3–4 min`  
**Performance improvement:** about **17×**

[Open project](https://github.com/GriGkos/GasPipelineBalancer)

---

### SOMA Optimizer

**Implementation and visualization of the Self-Organizing Migrating Algorithm for global optimization.**  
`Python` · `NumPy` · `Matplotlib` · `Global Optimization`

The project implements population-based optimization and visualizes the migration process on benchmark objective functions. It includes functions such as Schwefel, Rosenbrock, Rastrigin, Griewank and Ackley.

[Open project](https://github.com/GriGkos/SOMA-optimizer)

---

## How I approach ML experiments

1. Start with a clear question and a simple baseline.
2. Keep preprocessing fold-safe and avoid target leakage.
3. Compare models on the same validation splits.
4. Measure where the improvement comes from: data, features, model family or ensembling.
5. Use interpretation and error analysis instead of treating the final metric as the whole result.
6. Prefer a simpler model when a more complex one does not show a stable improvement.

---

## Stack

**Machine Learning**  
`scikit-learn` · `LightGBM` · `XGBoost` · `CatBoost` · `Optuna`

**Deep Learning**  
`PyTorch`

**Data & Analysis**  
`pandas` · `NumPy` · `SHAP` · `Matplotlib` · `Jupyter`

**Engineering**  
`Git` · `Docker` · `CUDA` · `Excel automation`

---

### More ML work

The full collection — from ML foundations to complete Kaggle pipelines — is available in [`GriGkos/ml-projects`](https://github.com/GriGkos/ml-projects).
