<p align="center">
  <img src="assets/project-banner.png" alt="Peripheral Nerve Impairment Severity Classification" width="100%">
</p>

# 🧠 Peripheral Nerve Impairment Severity Classification

### Multi-Class Severity Classification of Peripheral Nerve Impairment Using Multimodal Electrodiagnostic Features and Explainable Machine Learning

An explainable machine learning framework for classifying upper-extremity peripheral nerve impairment into four severity levels using Electromyography (EMG), Nerve Conduction Study (NCS), and integrated electrodiagnostic features.

<p align="center">
  <img src="https://img.shields.io/badge/Python-Machine%20Learning-blue?logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Explainable%20AI-SHAP-purple">
  <img src="https://img.shields.io/badge/Data-EMG%20%7C%20NCS-green">
  <img src="https://img.shields.io/badge/Task-Multi--Class%20Classification-orange">
  <img src="https://img.shields.io/badge/Research-Published-success">
</p>

---

## 📌 Overview

Peripheral nerve impairment assessment relies heavily on the interpretation of electrodiagnostic tests by specialized clinicians. This project explores the use of machine learning to support objective and interpretable severity classification based on EMG and NCS measurements.

The framework classifies peripheral nerve impairment into four classes:

- **Normal**
- **Mild**
- **Moderate**
- **Severe**

Three data configurations were investigated:

- EMG-derived features
- NCS-derived features
- Integrated EMG–NCS features

---

## 📊 Dataset

The study evaluated three clinical electrodiagnostic datasets:

| Dataset | Samples | Features |
|---|---:|---:|
| EMG | 912 | 10 |
| NCS | 1,020 | 13 |
| Integrated EMG–NCS | 28 | 17 |

The data were derived from anonymized clinical electrodiagnostic records.

> **Note:** The clinical datasets are not included in this repository to protect patient privacy and comply with research ethics requirements.

---

## ⚙️ Machine Learning Pipeline

The study followed a structured machine learning workflow across EMG, NCS, and integrated EMG–NCS data.

<p align="center">
  <img src="assets/methodology-workflow.png" alt="Machine Learning Methodology Workflow" width="85%">
</p>

<p align="center">
  <em>Overall methodology for data preprocessing, feature selection, model development, validation, and evaluation.</em>
</p>

---

## 🤖 Models

Five machine learning classifiers were evaluated:

- Support Vector Machine (SVM)
- Random Forest
- XGBoost
- LightGBM
- TabPFN

A performance-weighted ensemble of selected models was also evaluated.

---

## 📈 Key Results

### EMG

The ensemble of **SVM, Random Forest, and TabPFN** achieved:

- **Accuracy:** 73.77%
- **Macro F1-score:** 72.64%
- **AP Severe:** 88.82%

### NCS

**TabPFN** achieved the strongest standalone performance:

- **Accuracy:** 98.04%
- **Macro F1-score:** 98.60%
- **MCC:** 97.20%
- **AP Severe:** 100%

<p align="center">
  <img src="assets/ncs-tabpfn-confusion-matrix.jpg" alt="NCS TabPFN Test Confusion Matrix" width="70%">
</p>

<p align="center">
  <em>Confusion matrix of the final TabPFN model on the NCS test set.</em>
</p>

The results demonstrate the strong discriminative capability of NCS-derived features for peripheral nerve impairment severity classification.

---

## 🔍 Explainable AI

SHAP (SHapley Additive exPlanations) was used to interpret model predictions and identify the electrodiagnostic features contributing most strongly to severity classification.

Key findings included:

- **MUAP polyphasia percentage** was the dominant EMG predictor.
- **Sensory and motor latency** were among the most influential NCS predictors.
- Conduction velocity measurements also played an important role in distinguishing severity levels.

This explainability component helps connect machine learning predictions with clinically meaningful electrodiagnostic characteristics.

<p align="center">
  <img src="assets/ncs-severe-shap.jpg" alt="NCS Severe Class SHAP Plot" width="75%">
</p>

<p align="center">
  <em>SHAP summary plot for the Severe class using NCS features.</em>
</p>

---

## 🔗 Multimodal EMG–NCS Analysis

Only **28 paired EMG–NCS clinical records** were available for multimodal analysis.

To investigate the feasibility of multimodal learning under this limited-data setting, synthetic data generation approaches were evaluated, including:

- SMOTE
- Kernel Density Estimation (KDE)
- Gaussian Copula

Synthetic augmentation was applied only to training data to prevent data leakage.

Due to the small number of real paired records, the integrated analysis should be considered a **proof of concept** requiring validation on larger clinical cohorts.



## 🛠️ Technologies

### Programming & Analysis
- Python
- Jupyter Notebook
- Google Colab

### Machine Learning
- Scikit-learn
- XGBoost
- LightGBM
- TabPFN

### Explainable AI
- SHAP

### Data Analysis
- Pandas
- NumPy
- SciPy

## 📄 Publication

This project resulted in a peer-reviewed research publication in **Neurological Research**.

**Title:**  
*Multi-Class Severity Classification of Peripheral Nerve Impairment Using Multimodal Electrodiagnostic Features and Explainable Machine Learning*

**Journal:** Neurological Research  
**Published online:** August 4, 2026  
**DOI:** [10.1080/01616412.2026.2712459](https://doi.org/10.1080/01616412.2026.2712459)

<p align="center">
  <a href="https://doi.org/10.1080/01616412.2026.2712459">
    <img src="https://img.shields.io/badge/View-Published%20Article-blue">
  </a>
</p>

## 👥 Authors

Alanoud S. Almakadi · Dana S. Alnemari · Nadine T. Alsahafi · Salma N. Almutairi · Sarah M. Sadik · Noura M. Alotaibi · Ali N. Alshammari

**Affiliation:** Computer Science and Artificial Intelligence Department, University of Jeddah, Jeddah, Saudi Arabia.

> The first five authors contributed equally to this work.
