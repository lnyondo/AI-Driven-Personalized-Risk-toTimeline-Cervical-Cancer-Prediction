# AI-Driven-Personalized-Risk-toTimeline-Cervical-Cancer-Prediction
## Project Description
In this group project, we focused on cervical cancer prediction modelling by establishing the foundation for a personalized Risk-to-Timeline framework. The main objective was to determine whether population-level risk factors and clinical test results can be applied to generate more dynamic predictions of Cervical Intraepithelial Neoplasia (CIN) and support individualized follow-up recommendations.

Using the publicly available UCI Cervical Cancer Risk Factors dataset which contains demographic, behavioral, sexual health, and diagnostic variables including Hinselmann, Schiller, cytology, and biopsy outcomes, we developed a modeling pipeline capable of handling the dataset’s significant noise, sparsity, and class imbalance. The workflow included extensive data cleaning, preprocessing across mixed feature types, and imbalance-mitigation techniques to reduce bias. Several machine learning models were evaluated using cross-validation, and SHAP interpretability was incorporated to enhance transparency and clinical understanding.

Overall, the project identifies the most reliable model for predicting CIN risk and lays the methodological groundwork for future development of personalized, time-based R-to-T models that support precision prevention and more equitable cervical cancer care.
##  Project Overview
Using the UCI Cervical Cancer Risk Factors dataset, The work establishes the first step toward a more advanced Risk-to-Timeline (R-to-T) model that will ultimately estimate individualized disease progression patterns. The full analysis was conducted in a Jupyter Notebook included in this repository.

The project focuses on:
- Cleaning and standardizing a noisy, highly imbalanced dataset
- Evaluating a diverse set of nine machine-learning algorithms
- Using cross-validation for reliable performance estimates
- Identifying the most trustworthy model for CIN prediction
- Applying SHAP to improve interpretability and clinical transparency


## Dataset Summary
- Dataset: UCI Cervical Cancer Risk Factors
- Total records: 858
- Features: 36 demographic, behavioral, STI-related, and diagnostic variables
- Target variable: Dx:CIN
- Positive cases: Only 9 (≈1%)[Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf](https://github.com/user-attachments/files/23973184/Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf)


## Preprocessing Workflow

### 1. Missing value handling
- Replaced ? with NaN
- Removed two columns with >90% missing values
- Applied median imputation to remaining numeric variables

### Data type correction
- Converted object-type columns to numeric
- Cleaned column names (removed non-breaking spaces and inconsistencies)

### Class imbalance strategy
- 80/20 stratified split
- Applied SMOTE on the training set (10% minority sampling)
- Computed class weights to penalize misclassification of CIN-positive cases

## Modelling Approach
Nine models were developed and compared:
1. Distance / Linear: KNN, Linear SVM
2. Kernel SVM: RBF, Sigmoid
3. Probabilistic: GaussianNB
4. Tree-based: Decision Tree, Gradient Boosting
5. Neural Network: MLP
6. Imbalance-aware Ensemble: Easy Ensemble
   
- All models used streamlined Scikit-Learn pipelines with scaling and optional class weighting.

## Evaluation Strategy
Two evaluation stages were used:
### A. Stratified 80/20 Split
Produced near-perfect scores across most models because the test set contained only two positive samples, making accuracy misleading.
### B. 3-Fold Stratified Cross-Validation
Provided a far more stable and meaningful assessment using:
- Precision
- Recall
- F1-score
- Accuracy
### Key Finding
Linear SVM outperformed all other models, showing the best balance between correctly identifying CIN-positive samples and minimizing false positives.

## Explainability Using SHAP
SHAP was applied to the final Linear SVM model to interpret individual and global predictions and to ensure the model's decisions aligned with established clinical risk patterns..
Top contributing features included:
1. HPV-related diagnostic indicators
2. Previous abnormal diagnostic findings (e.g., Dx, Dx:Cancer, Dx:HPV)
3. Abnormal screening results (Hinselmann, Schiller, Cytology, Biopsy)
4. Behavioral factors such as smoking and STD history

## Summary of Key results
| Model          | Recall (CIN+) | Precision (CIN+) | F1-Score  | Notes                            |
| -------------- | ------------- | ---------------- | --------- | -------------------------------- |
| **Linear SVM** | **1.00**      | **0.917**        | **0.952** | Most stable across folds         |
| RBF SVM        | 0.889         | 1.00             | 0.933     | Lower recall                     |
| Decision Tree  | 1.00          | 0.833            | 0.905     | More false positives             |
| Easy Ensemble  | 1.00          | 0.40             | 0.565     | High recall, low specificity     |
| Others         | varied        | varied           | varied    | Underperformed on minority class |

## Future Directions
- Incorporating longitudinal data for true timeline modelling
- Exploring survival analysis and time-aware ML
- Increasing CIN-positive sample size
- Performing external validation
- Integrating the model into a clinical decision-support tool

### Documents
[Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf](https://github.com/user-attachments/files/23973185/Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf)

[Personalized Risk-to-timeline modelling for cervical cancer progression_ Predicting outcomes from clinical and population risk factors.pdf](https://github.com/user-attachments/files/23973195/Personalized.Risk-to-timeline.modelling.for.cervical.cancer.progression_.Predicting.outcomes.from.clinical.and.population.risk.factors.pdf)

[Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf](https://github.com/user-attachments/files/23973194/Cervical_Cancer_Risk_to_Timeline_Presentation.pptx.pdf)

YouTube Video Link: https://youtu.be/hKEceJ-mNhw 
