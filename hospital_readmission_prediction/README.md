# README - Hospital Readmission Prediction

## Overview  
This project focuses on predicting hospital readmissions within 30 days for diabetic patients using machine learning techniques. The code implements a comprehensive data processing pipeline and evaluates multiple ensemble models to achieve the best prediction performance.

## Key Features  
- Data preprocessing and feature engineering pipeline  
- Stacking ensemble model using multiple base classifiers  
- Evaluation metrics focused on F1-score
- Prediction on test data (`readmission test.csv`)

## Data Processing Pipeline  

**1. `map_readmitted(df)` - Relevant only when ruuning plots for training data**  
Converts the target variable ('readmitted') to binary values:  
- 1 if readmitted within 30 days ('<30')  
- 0 otherwise ('NO' or '>30')

**2. `handling_missing_values(df_target_incode)`**  
Handles missing values by:  
- Dropping the `'weight'` column (too many missing values)  
- Filling `'payer_code'` and `'medical_specialty'` with `'Unknown'`  
- Filling `'race'` with the most frequent value

**3. `feature_engineering(df_cleaned)`**  
Performs feature encoding:  
- Label encoding for categorical variables (race, gender)  
- Ordinal encoding for age bins  
- One-hot encoding for medication columns and other categorical features

**4. `normalization(df_encoded)`**  
Applies standard scaling to numerical features:  
- `time_in_hospital`, `num_lab_procedures`, `num_procedures`, `num_medications`  
- Visit metrics (`number_outpatient`, `number_emergency`, `number_inpatient`)

**5. `diag_treatment(df_normalization)`**  
Processes diagnosis codes (`diag_1`, `diag_2`, `diag_3`):  
- Cleans ICD codes by removing leading `'V'` or `'E'`  
- Converts to numeric values  
- Applies standard scaling

**6. `outlier_treatment(df_diag)`**  
Removes outliers using Z-score method (threshold = 2)

## Stacking Ensemble (Best Performing Model)  
Combines predictions from multiple base models using Logistic Regression as meta-learner.

### Base Models  
- **Random Forest** (100 trees)  
- **Extra Trees** (100 trees)  
- **XGBoost**  
- **AdaBoost** (100 estimators)  
- **Gradient Boosting** (100 estimators, learning rate = 0.1)

### Performance  
- **F1-score (readmitted=1)**: 0.9380  

## Data Files Used  
- **Training data**: `readmission training.csv`  
- **Test data**: `readmission test.csv`  
- **Submission file**: `submission file.csv`

## How to Run  
1. Ensure all required packages are installed  
2. Place data files in the correct directory  
3. Run the notebook sequentially  
4. Predictions will be saved to `submission file.csv`
