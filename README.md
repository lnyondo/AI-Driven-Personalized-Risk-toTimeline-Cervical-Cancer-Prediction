# AI-Driven-Personalized-Risk-toTimeline-Cervical-Cancer-Prediction
## Project Description
In this group project, we focused on cervical cancer prediction modelling by establishing the foundation for a personalized Risk-to-Timeline framework. The main objective was to determine whether population-level risk factors and clinical test results can be applied to generate more dynamic predictions of Cervical Intraepithelial Neoplasia (CIN) and support individualized follow-up recommendations.

Using the publicly available UCI Cervical Cancer Risk Factors dataset which contains demographic, behavioral, sexual health, and diagnostic variables including Hinselmann, Schiller, cytology, and biopsy outcomes, we developed a modeling pipeline capable of handling the dataset’s significant noise, sparsity, and class imbalance. The workflow included extensive data cleaning, preprocessing across mixed feature types, and imbalance-mitigation techniques to reduce bias. Several machine learning models were evaluated using cross-validation, and SHAP interpretability was incorporated to enhance transparency and clinical understanding.

Overall, the project identifies the most reliable model for predicting CIN risk and lays the methodological groundwork for future development of personalized, time-based R-to-T models that support precision prevention and more equitable cervical cancer care.
##  Project Overview
Using the UCI Cervical Cancer Risk Factors dataset, The work establishes the first step toward a more advanced Risk-to-Timeline (R-to-T) model that will ultimately estimate individualized disease progression patterns. The full analysis was conducted in a Jupyter Notebook included in this repository.

The project focuses on:

-- Cleaning and standardizing a noisy, highly imbalanced dataset
-- Evaluating a diverse set of nine machine-learning algorithms
-- Using cross-validation for reliable performance estimates
-- Identifying the most trustworthy model for CIN prediction
-- Applying SHAP to improve interpretability and clinical transparency

## Dataset Summary
-- Dataset: UCI Cervical Cancer Risk Factors
-- Total records: 858
-- Features: 36 demographic, behavioral, STI-related, and diagnostic variables
-- Target variable: Dx:CIN
-- Positive cases: Only 9 (≈1%)

