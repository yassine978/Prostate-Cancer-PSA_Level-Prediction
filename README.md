# 🧬 Prostate Cancer – PSA Level Prediction

This project focuses on building predictive models to estimate **PSA levels** (log-transformed `lpsa`) for patients with prostate cancer using clinical and histological features. It was developed as part of the **M1 Big Data & AI** program at *Université Paris Dauphine | Tunis*.

> PSA (Prostate-Specific Antigen) is a key biomarker for diagnosing and monitoring prostate cancer progression. Accurate modeling of PSA levels can support medical decision-making.

---

## 🎯 Project Objectives

- 📈 Predict the continuous variable `lpsa` (log of PSA) from 8 patient features.
- 🔍 Identify key factors influencing PSA levels.
- ⚖️ Compare linear and nonlinear regression models.
- 📊 Apply explainable AI (SHAP, LIME) to interpret model predictions.
- 🧪 Use robust validation techniques and regularization.

---

## 🧪 Dataset Description

- **Source**: `prostate.csv` from the `lasso2` R package
- **Samples**: 97 patients (67 train / 30 test)
- **Features**:
  - `lcavol`: Log cancer volume
  - `lweight`: Log prostate weight
  - `age`: Age of patient
  - `lbph`: Log benign prostatic hyperplasia amount
  - `svi`: Seminal vesicle invasion (0/1)
  - `lcp`: Log capsular penetration
  - `gleason`: Gleason score
  - `pgg45`: % of Gleason score 4 or 5

---

## 🧠 Models Used & Results Summary

| Model            | RMSE   | MAE    | R²     |
|------------------|--------|--------|--------|
| Linear Regression | 0.521  | 0.57   | 0.503 |
| Lasso Regression  | 0.501  | 0.55   | 0.522 ✅ Best |
| Ridge Regression  | 0.522  | 0.57   | 0.502 |
| ElasticNet        | 0.521  | 0.56   | 0.504 |
| Random Forest     | 0.764  | 0.58   | 0.44  |
| SVR (linear kernel) | 0.720 | 0.55  | 0.506 |

> ✅ **Lasso Regression** provided the best performance with interpretability and regularization.

---

## 🛠 Techniques & Tools

### 🔍 Exploratory Data Analysis (EDA)
- Histograms, boxplots, scatterplots
- Correlation matrix
- Distribution analysis of `lpsa` vs features

### ⚙️ Modeling Pipeline
- Standardization (StandardScaler)
- Train/test split based on the `train` column
- Hyperparameter tuning (GridSearchCV, LassoCV, RidgeCV, ElasticNetCV)
- Cross-validation analysis

### 📊 Interpretability
- **SHAP** (global & local explanation)
- **LIME** (explanation for specific patient predictions)
- **Coefficient plots & confidence intervals**
- **Variance Inflation Factor (VIF)** analysis for multicollinearity

---

## 📈 Key Insights

- `lcavol`, `lweight`, and `svi` are the most predictive features across models.
- Nonlinear models (Random Forest, SVR) did not outperform simpler linear models — indicating primarily **linear relationships** in the data.
- Regularization (Lasso) improved generalization while maintaining interpretability.

---

## 🔬 Tools and Libraries

- `scikit-learn`
- `statsmodels`
- `pandas`, `matplotlib`, `seaborn`
- `shap`, `lime`
- `numpy`, `scipy`

---

## 💡 What I Learned

- Applied multiple regression techniques and model tuning
- Leveraged SHAP & LIME for explainable machine learning
- Used statistical diagnostics (p-values, VIF) to validate models
- Communicated results using plots and evaluation metrics
- Learned trade-offs between interpretability and performance
---

