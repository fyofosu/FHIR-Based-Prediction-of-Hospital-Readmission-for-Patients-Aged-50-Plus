# FHIR-Based-Prediction-of-Hospital-Readmission-for-Patients-Aged-50-Plus
Hospital readmissions, especially within 30 days of discharge, are a major concern both for patient health and hospital systems. In this project, we use AI to predict the likelihood of readmission by analyzing clinical data structured in FHIR format. 
Hospital readmissions, especially within 30 days of discharge, are a major concern both for patient health and hospital systems. In this project, we use AI to predict the likelihood of readmission by analyzing clinical data structured in FHIR format.
# Project Presentation
https://youtu.be/ruE4aTEJlw4

# 📚 Literature Review

Research into AI for hospital readmission prediction has shown promising results:

Michailidis et al. achieved an AUC of 0.78 using Random Forest models with administrative and clinical data.

Mahmoudi et al. reviewed 41 studies showing that machine learning often outperforms traditional statistical methods.

Integration of wearable device data (e.g., heart rate entropy) has enhanced prediction accuracy.

Saati et al. emphasized that reducing unnecessary ED visits and readmissions could significantly lower costs and improve outcomes.

AI's role in healthcare continues to expand, offering automation and insights across clinical tasks.

This project builds on these advances, applying the FHIR standard to enable scalable, interoperable prediction pipelines.

# 🎯 Problem Statement

30-day hospital readmissions remain a costly and preventable issue in the healthcare system. Existing scoring systems (e.g., LACE, HOSPITAL score) are limited in personalization and do not leverage structured EHR data effectively. This project addresses that gap by: Utilizing detailed patient-level FHIR data
Creating a predictive model for hospital readmission in aged patients with chronic conditions

# 👥 Justification of Population Chosen

We chose patients aged 50 years and above with chronic conditions due to:

Their elevated risk for readmissions

The burden they place on post-acute care systems

The clinical importance of targeting preventive strategies toward this group

This focus aligns with real-world hospital quality improvement efforts and value-based care initiatives.

# 📊 Dataset: FHIR_Readmission_Prediction_Dataset

FHIR-converted JSON data was extracted from:

CCDA (Clinical Document Architecture)

ADT (Admission/Discharge/Transfer)

ORU (Observation Result messages)

Data was standardized and structured to produce a CSV-format dataset with the following key features:

Demographics (age, sex)

Chronic conditions and comorbidities

Prior admissions

Laboratory values and vital signs

Timestamps for readmission labeling

# ✅ Dataset Validation

To ensure quality and reliability:

Completeness Check: Ensured that mandatory fields (e.g., patient ID, timestamps, age) were populated

Consistency Check: Cross-validated encounter types, lab values, and comorbidities across messages

Temporal Validity: Ensured encounter dates were within realistic healthcare practice periods

Feature Importance: Used correlation and model-based feature importance scoring to validate predictive power

# 🔧 Methodology

Data Preprocessing

Merged patient-level FHIR data from 2,000+ JSON files

Removed duplicates and non-numeric features

Filtered patients under 50 or without chronic conditions

Normalized lab values and vital signs

Feature Engineering

Computed average lab values per LOINC code

Created binary flags for chronic conditions

Simulated or derived readmission labels based on encounter timestamps

Model Training

Trained and tuned multiple models:

Random Forest

Gradient Boosting

XGBoost

MLP Neural Net

SVM, KNN, Naive Bayes, Logistic Regression

Model Evaluation

Used SMOTE for class balancing

Evaluated using:

AUC (ROC): Up to 0.87

F1 Score: Up to 0.69

Recall: Prioritized for minimizing false negatives

Confusion Matrix: Assessed sensitivity vs. specificity

Visualization

ROC curves for all models

Feature importance for top contributors (e.g., creatinine, heart rate)

# 🔍 Findings & Interpretation

Tree-based models (Random Forest, Gradient Boosting) significantly outperformed linear models

Feature importance analysis showed that lab data (e.g., creatinine, oxygen saturation) and chronic flags were strongest predictors

Filtering to patients aged 80+ increased model specificity

AUC scores (~0.87) are competitive with or better than published models

# 🔭 Future Work

Incorporate NLP for unstructured clinical notes

Explore Federated Learning for data-sharing across institutions

Assess model deployment impact in clinical settings

Include medication data and social determinants of health

# 🔗 References

Forecasting Hospital Readmissions with Machine Learning. PMC

Prediction of Unplanned Hospital Readmission Using Clinical and Longitudinal Wearable Sensor Features. PMC

Commercial Hospital AI System Impact on Readmissions. Rutgers RUcore

ClinicalBERT for Clinical Notes. ArXiv

Deep Learning for Hospital Readmission. IEEE Xplore

Effective Models Using Machine-learned Features. BioMed Central
