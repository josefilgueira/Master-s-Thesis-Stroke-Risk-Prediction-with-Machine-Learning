# Master’s Thesis – Stroke Risk Prediction with Machine Learning

This repository contains my **Master’s Thesis (TFM)** developed for the MSc in Data Science, Big Data and Business Analytics at Universidad Complutense de Madrid.

The project focuses on **predicting the risk of stroke (ictus)** using supervised machine learning models applied to clinical and lifestyle data. The work combines exploratory data analysis, careful preprocessing, model comparison, and interpretability considerations, with an emphasis on methodological rigor and clinical plausibility.

---

## 🎯 Objective

The main goal of this project is to develop and evaluate predictive models capable of estimating the probability of suffering a stroke based on demographic, clinical, and lifestyle variables.

Given the strong class imbalance inherent to medical datasets of this type, special attention is paid to:
- appropriate evaluation metrics,
- robust validation strategies,
- and interpretability of results.

---

## 📁 Dataset

The analysis uses the **Healthcare Dataset – Stroke Data**, a publicly available dataset containing **5,110 patient records**.

**Target variable:**
- `stroke` (binary: 0 = no stroke, 1 = stroke)

**Key features include:**
- Age
- Gender
- Hypertension
- Heart disease
- Average glucose level
- Body Mass Index (BMI)
- Smoking status
- Marital status
- Work type
- Residence type

Notable dataset characteristics:
- Strong class imbalance (~5% positive cases)
- Missing values in the BMI variable
- Mix of numerical and categorical features

---

## 🔍 Project Structure & Methodology

### 1. Exploratory Data Analysis (EDA)
- Analysis of distributions and missing values
- Study of class imbalance and its implications
- Univariate and bivariate analysis of key risk factors
- Identification of clinically meaningful patterns (age, glucose, hypertension, heart disease)

### 2. Data Preprocessing & Feature Engineering
- Removal of non-informative identifiers
- **Model-based imputation of BMI** using a Random Forest regressor
- Creation of a winsorized BMI version to reduce the impact of outliers
- Discretization of glucose levels into interpretable clusters
- One-hot encoding of categorical variables
- Standardization of numerical features where required
- Fully reproducible preprocessing pipeline to avoid data leakage

### 3. Modeling
Several supervised classification models are trained and compared under the same preprocessing pipeline:
- Logistic Regression (with class weighting)
- Random Forest
- Histogram-based Gradient Boosting

Key aspects:
- Stratified cross-validation
- Class imbalance handling via weighted loss functions
- Evaluation on a held-out test set

### 4. Evaluation Metrics
Given the imbalance of the target variable, the evaluation prioritizes:
- **PR-AUC (Precision–Recall AUC)** as the main metric
- ROC-AUC
- Recall, Precision, and F1-score

Logistic Regression achieved the best overall balance between discrimination, recall, and interpretability.

### 5. Interpretability
- Analysis of feature importance and model coefficients
- Identification of the most influential predictors:
  - Age
  - Average glucose level
  - BMI
  - Hypertension history
- Discussion of results from a clinical and practical perspective

---

## 🧠 Key Learnings

This project allowed me to:
- Apply machine learning techniques to a **real-world healthcare problem**
- Handle **highly imbalanced medical data** responsibly
- Build reproducible preprocessing pipelines
- Compare interpretable and non-linear models
- Balance predictive performance with clinical interpretability

The work emphasizes **methodological soundness and transparency** over model complexity.

---

## 🛠️ Tools & Technologies

- **Python**
- **Pandas & NumPy** – data manipulation
- **Scikit-learn** – preprocessing, modeling, evaluation
- **Matplotlib & Seaborn** – data visualization
- **Jupyter Notebook** – experimentation and documentation

---

## 📁 Repository Contents

- `CODIGO_HTML_TFM_JOSE_FILGUEIRA_ORGE.html` – Full notebook exported to HTML  
- `INFORME_TFM_JOSE_FILGUEIRA_ORGE.pdf` – Master’s Thesis report  
- `healthcare-dataset-stroke-data.csv` – Dataset used in the analysis  

---

## ⚠️ Limitations & Future Work

- The dataset size limits the complexity of models that can be reliably trained
- External validation on independent cohorts would be required for real-world deployment
- Future work could explore:
  - calibration techniques,
  - more advanced imbalance handling,
  - integration with clinical decision-support systems.

---

## 👤 Author

**Jose Filgueira Orge**  
MSc in Data Science, Big Data & Business Analytics  
Universidad Complutense de Madrid
