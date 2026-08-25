# Konstantin Grigorchak

**ML Engineer / Data Scientist**

I build machine-learning solutions and AI-backed applications around real data and engineering constraints. My public work covers **tabular ML, model validation, LLM agents, backend integration, numerical methods and automation**.

I care about reproducible experiments, leakage-safe validation and understanding **where an improvement actually comes from** — data, features, model choice or ensembling — rather than simply trying more algorithms.

Main stack: `Python` · `PyTorch` · `scikit-learn` · `LightGBM` · `XGBoost` · `CatBoost` · `FastAPI` · `PostgreSQL` · `Docker`

---

## Selected projects

### Home Credit Default Risk

**Credit-risk scoring using current application data and detailed customer credit history.**  
`CatBoost` · `LightGBM` · `PyTorch` · `Optuna` · `SHAP` · `Permutation Importance`

- **OOF ROC-AUC:** `0.79405`
- **Kaggle Private:** `0.79510`
- final feature matrix: **2,708 features**
- compared Logistic Regression, Decision Tree, LightGBM, CatBoost and MLP on the same 5-fold OOF scheme
- measured the contribution of historical data separately from model complexity
- used cross-fitted blending, calibration analysis, SHAP, grouped permutation importance, FP/FN analysis and fairness diagnostics

Detailed credit history improved LightGBM by **+0.01814 ROC-AUC** over the application-only setup. A CatBoost + LightGBM blend slightly improved OOF but did not improve the hidden Kaggle leaderboard, so CatBoost remained the final model.

[Open project](https://github.com/GriGkos/ml-projects/tree/main/projects/04_home_credit_scoring)

---

### Mail Task Agent

**AI backend that converts incoming email into persistent tasks and uses human approval for uncertain actions.**  
`FastAPI` · `LangGraph` · `PostgreSQL` · `SQLAlchemy` · `Gmail API` · `Microsoft Graph` · `Telegram` · `Docker`

- Gmail and Outlook integrations with OAuth-based account connection
- Pydantic-validated LLM decisions with explicit routing between automatic and review-required actions
- persistent tasks, task events, approvals and agent-run audit logs in PostgreSQL
- Telegram human-in-the-loop approval flow
- safe `DRY_RUN` mode, restricted mailbox processing and idempotent callbacks
- encrypted storage for connected-mail OAuth credentials
- single-user mode plus a multi-user onboarding foundation
- automated tests around email processing, onboarding, providers, routing, persistence and Telegram integration

The project deliberately limits autonomous actions: the current MVP does not automatically send, delete or archive email. The focus is on **observable decisions, persistent state and recoverable backend behavior**.

[Open project](https://github.com/GriGkos/mail-task-agent)

---

### Elo Merchant Category Recommendation

**Customer-loyalty regression from large-scale transaction history.**  
`XGBoost` · `LightGBM` · `CatBoost` · `Optuna` · `Target Encoding` · `Bootstrap`

- processed more than **29 million historical transactions**
- built card-level aggregates from large tables using chunked processing
- compared LightGBM, XGBoost and CatBoost with Optuna tuning
- implemented fold-safe target encoding, seed bagging, weighted blending and stacking
- checked whether a small ensemble gain was statistically meaningful with paired bootstrap

**Kaggle Private RMSE:** `3.60826`  
**Private leaderboard:** **82 / 4,111 — Top 1.99%**

The more complex stacking solution had the best raw OOF score, but its advantage over XGBoost seed bagging was not statistically stable. I kept the simpler solution for the final submission.

[Open project](https://github.com/GriGkos/ml-projects/tree/main/projects/03_elo_merchant)

---

### Gas Pipeline Balancer

**Python replacement for an Excel/VBA workflow used to balance gas pipeline systems.**  
`Python` · `Numerical Methods` · `Xlwings` · `Excel Automation`

- replaced a rigid VBA macro with a Python tool
- processes coefficient ranges instead of calculating values one by one
- uses Newton's method for faster convergence
- supports several calculation modes and configurable subsystem priorities
- integrates with the existing Excel-based workflow

**Computation time:** `40–50 min → 3–4 min`  
**Performance improvement:** about **17×**

[Open project](https://github.com/GriGkos/GasPipelineBalancer)

---

## Selected technical work

### SQL / PostgreSQL

[`DB-SQL-practicum`](https://github.com/GriGkos/DB-SQL-practicum) — joins, subqueries, analytical window functions, views, set operations, recursive queries and `EXPLAIN ANALYZE`.

### Forecasting and statistical modeling

[`Forecasting-practicum`](https://github.com/GriGkos/Forecasting-practicum) — least squares, statistical significance, confidence intervals, residual diagnostics, ACF/PACF and classical AR/MA time-series models.

### Numerical optimization

[`SOMA-optimizer`](https://github.com/GriGkos/SOMA-optimizer) and [`DFP-BFGS-optimizer`](https://github.com/GriGkos/DFP-BFGS-optimizer) — implementations and experiments with global and quasi-Newton optimization methods.

---

## How I approach ML experiments

1. Start with a clear question and a simple baseline.
2. Keep preprocessing fold-safe and avoid target leakage.
3. Compare models on the same validation splits.
4. Measure where the improvement comes from: data, features, model family or ensembling.
5. Use interpretation and error analysis instead of treating the final metric as the whole result.
6. Prefer a simpler solution when extra complexity does not show a stable improvement.

---

## Stack

**Machine Learning**  
`scikit-learn` · `LightGBM` · `XGBoost` · `CatBoost` · `Optuna`

**Deep Learning**  
`PyTorch`

**Data & Analysis**  
`pandas` · `NumPy` · `SQL` · `PostgreSQL` · `SHAP` · `Matplotlib` · `Jupyter`

**AI / Backend**  
`FastAPI` · `Pydantic` · `SQLAlchemy` · `LangGraph` · `REST APIs`

**Engineering**  
`Git` · `Docker` · `CUDA` · `Excel automation`

---

### More ML work

The full collection — from ML foundations to complete Kaggle pipelines — is available in [`GriGkos/ml-projects`](https://github.com/GriGkos/ml-projects).
