# Early Sepsis Detection Project

This repository focuses on sepsis onset prediction in ICU patients using the PhysioNet 2019 Challenge dataset. It implements and benchmarks multiple ML models, with well-documented Jupyter notebooks covering data preprocessing, missing value imputation, feature engineering, class imbalance handling, and evaluation using metrics like recall, precision, and F1-score.

---

## 📁 Repository Structure

```
Advika1030_Final_Project/
│
├── Analyzing_data (1).ipynb         # Data exploration & preprocessing
├── logistic regression.ipynb        # Baseline model: Logistic Regression
├── xgboost.ipynb                    # Baseline model: XGBoost
├── xgboost_interpolated.ipynb       # XGBoost with missing‐value interpolation
├── xgboost_recall_optimisation.ipynb# XGBoost tuned for recall optimization
├── ppt.pdf                          # Presentation slides summarizing methods & results
├── README.md                        # This file

```

---

## 📝 Overview

Early detection of sepsis can dramatically improve patient outcomes. In this project, we:

1. **Load and explore** the PhysioNet 2019 ICU vital‐sign dataset.
2. **Impute missing values** using techniques like MICE and linear interpolation.
3. **Train and compare** several models:

   * Logistic Regression (balanced classes)
   * XGBoost (default hyperparameters)
   * XGBoost with data interpolation
   * XGBoost tuned for high recall
4. **Evaluate** models on accuracy, recall, precision, F1 score, and confusion matrices.
5. **Present** findings and trade‐offs in the `ppt.pdf` slides.

---

## 🚀 Getting Started

1. **Run notebooks** in order:

   1. `Analyzing_data (1).ipynb` – exploratory data analysis, missingness patterns, class imbalance
   2. `logistic regression.ipynb` – train logistic regression with balanced classes
   3. `xgboost.ipynb` – baseline XGBoost performance
   4. `xgboost_interpolated.ipynb` – evaluate interpolation strategies before modeling
   5. `xgboost_recall_optimisation.ipynb` – hyperparameter tuning to maximize recall

---

## 📊 Data

* **Source**: PhysioNet 2019 Sepsis Early Prediction Challenge
* **Format**: CSV/PSV files with hourly ICU measurements and binary sepsis label
* **Preprocessing**:

  * Merging multiple CSVs into a single DataFrame
  * Handling missing values via forward‐fill, linear interpolation, and MICE
  * Feature scaling/normalization where required

Refer to the data‐loading sections in `Analyzing_data (1).ipynb` for full pipeline.

---

## 🧠 Methodology

1. **Exploratory Data Analysis**:

   * Visualize missingness patterns
   * Compute class imbalance ratio
   * Examine feature distributions

2. **Imputation**:

   * **Forward/Backward fill** for short gaps
   * **Linear interpolation** for continuous signals
   * **MICE (Multivariate Imputation by Chained Equations)** for complex missing patterns

3. **Modeling**:

   * **Logistic Regression**: baseline, class‐weight adjustments
   * **XGBoost**: tree‐based ensemble, default vs. tuned hyperparameters
   * **Recall Optimization**: grid search targeting high recall (critical for sepsis detection)

4. **Evaluation**:

   * Confusion matrix analysis
   * Precision, recall, F1‐score, ROC‐AUC
   * Trade‐off discussion between sensitivity (recall) and false positives

---

## 📈 Results Summary

| Model                                 | Accuracy | Recall | Precision | F1‐Score | False -ve |
| ------------------------------------- | :------: | :----: | :-------: | :------: | :------:  | 
| Logistic Regression (balanced)        |   0.92   |  0.32  |    0.08   |   0.13   |   3745    |
| XGBoost (default)                     |   0.97   |  0.08  |    0.86   |   0.16   |   5347    |
| XGBoost + Interpolation (MICE)        |   0.98   |  0.07  |    0.17   |   0.10   |   5162    |
| XGBoost + Recall‐Optimized Hyperparam |   0.54   |  0.80  |    0.03   |   0.05   |   1084    |



---

## 📑 Presentation

Open `ppt.pdf` for a concise overview of objectives, methodology, and key findings. Slides include:

* Motivation & clinical importance
* Data challenges & pre‐processing steps
* Model comparisons
* Recommendations for deployment

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for details.
