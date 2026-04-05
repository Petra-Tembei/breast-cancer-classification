# Breast Cancer Tumor Classification

**Distinguishing malignant from benign tumors using cell nucleus morphology and machine learning**

---

## Overview

Fine needle aspiration (FNA) biopsy produces digitised images of cell nuclei from a breast mass.
This project uses 30 geometric measurements extracted from those images to train two classifiers —
**Logistic Regression** and an **SVM with RBF kernel** — and evaluates their ability to predict
whether a tumor is malignant or benign.

The analysis focuses equally on **model performance** and **clinical interpretability**: which
features drive predictions, where the models fail, and what those failures cost in a medical context.

---

## Dataset

| Property | Detail |
|---|---|
| Source | [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)) / `sklearn.datasets` |
| Samples | 569 |
| Features | 30 numeric (mean, SE, worst of 10 nucleus measurements) |
| Target | Binary - Malignant (0) / Benign (1) |
| Class balance | 37.3% malignant / 62.7% benign |

No external download required — the dataset is bundled with `scikit-learn`.

---

## Methods

- **EDA:** Class distribution, correlation heatmap, boxplots of key features by class
- **Preprocessing:** StandardScaler, stratified 80/20 train-test split
- **Model 1:** Logistic Regression (L2, lbfgs) — interpretable baseline
- **Model 2:** SVM with RBF kernel — non-linear discriminative boundary
- **Evaluation:** Classification report, confusion matrix, ROC curve, AUC, 5-fold cross-validation

---

## Results

| Model | Test AUC | Accuracy |
|---|---|---|
| Logistic Regression | ~0.995 | ~97% |
| SVM (RBF) | ~0.997 | ~98% |

Both models achieve near-ceiling performance. The Logistic Regression is preferred in
clinical contexts for its coefficient interpretability.

---

## Requirements

```
python >= 3.8
scikit-learn
pandas
numpy
matplotlib
seaborn
```

Install with:
```bash
pip install scikit-learn pandas numpy matplotlib seaborn
```

---

## Usage

Open `breast_cancer_classification.ipynb` in Jupyter Lab or Jupyter Notebook and run all cells.

```bash
jupyter notebook breast_cancer_classification.ipynb
```

---

## Project Structure

```
├── breast_cancer_classification.ipynb   # Main analysis notebook
├── eda_distributions.png                # Generated during run
├── eda_correlation.png
├── eda_boxplots.png
├── lr_coefficients.png
├── model_comparison.png
└── README.md
```
