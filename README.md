# Heart Failure Mortality Prediction
### A Comparative Analysis of Supervised Learning Models

## Project Overview
Cardiovascular diseases (CVDs) are the number one cause of death globally, taking an estimated 17.9 million lives each year. Heart failure is a common event caused by CVDs.

This project aims to build a machine learning model capable of predicting mortality in heart failure patients using clinical data. The goal is to identify high-risk patients early to enable timely intervention.

**Objective:** Predict DEATH_EVENT (0 = Survival, 1 = Death) based on 12 clinical features.

---

## Motivation: Bioinformatics & Longevity
As a graduate student passionate about Bioinformatics and Anti-Aging Research, I initially sought datasets related to biological age prediction or health span extension. However, high-quality public datasets in that specific niche are rare or require complex time-series analysis beyond the scope of this project.

I chose this Heart Failure dataset as a strategic proxy. Predicting mortality based on biomarkers is the inverse of studying longevity; by understanding the risk factors that lead to death (e.g., serum creatinine levels, ejection fraction), we gain insight into the biomarkers that define resilience and health.

---

## The Data
*   **Source:** Kaggle - Heart Failure Clinical Records
*   **Size:** 299 Patients
*   **Target:** Binary Classification (Imbalanced: ~68% Survival)
*   **Key Features:** Age, Ejection Fraction, Serum Creatinine, Serum Sodium.

---

## Methodology

### 1. Exploratory Data Analysis (EDA)
I analyzed feature correlations and distributions.
*   **Critical Finding:** The "time" variable (follow-up period) was identified as a source of Data Leakage and removed to ensure a realistic clinical prediction model.

### 2. Preprocessing
*   **Stratified Split:** Data was split 80/20 while maintaining the class ratio.
*   **Standardization:** Applied StandardScaler to normalize features, which proved critical for the performance of distance-based algorithms.

### 3. Model Comparison
I trained and evaluated three distinct classifiers:
*   Logistic Regression (Linear Baseline)
*   Random Forest Classifier (Ensemble)
*   Support Vector Machine (SVM) (High-Dimensional)

---

## Results
After feature scaling, the Support Vector Machine (SVM) emerged as the clear winner.

| Model | Accuracy | F1-Score |
| :--- | :--- | :--- |
| **SVM (Scaled)** | **0.75** | **0.55** |
| Logistic Regression | 0.70 | 0.44 |
| Random Forest | 0.70 | 0.44 |

*   **AUC Score:** 0.74
*   **Key Insight:** The initial SVM model failed (F1=0.0) on raw data. Standardization was the decisive factor that unlocked its performance.

---

## Project Structure

```text
heart-failure-prediction/
├── data/
│   └── heart_failure_clinical_records_dataset.csv
├── images/
│   ├── eda_heatmap.png
│   ├── eda_boxplots.png
│   ├── final_confusion_matrix.png
│   └── final_roc_curve.png
├── notebooks/
│   └── Final_Project_Heart_Failure.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE


Transparency Note

## Transparency Note
The video presentation accompanying this project was narrated using an AI voice clone of the author, generated via ElevenLabs. The slides were created with Google Slides, and the final video was assembled using Google Vids. This choice reflects my interest in leveraging AI tools for effective communication and accessibility.

Technologies Used

Language: Python 3.11

Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn

Environment: Jupyter Notebook

Author

Nick Shiva
Graduate Student in AI & Machine Learning
