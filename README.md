## Dataset
The dataset contains various patient attributes such as blood pressure, blood glucose, hemoglobin, and serum creatinine.

### Selected Features
- SocioeconomicStatus  
- EducationLevel  
- BMI  
- Smoking  
- PhysicalActivity  
- FamilyHistoryKidneyDisease  
- FamilyHistoryHypertension  
- UrinaryTractInfections  
- SystolicBP, DiastolicBP  
- FastingBloodSugar, HbA1c  
- SerumCreatinine  

Additional features correlated with the diagnosis (>0.02):  
- BUNLevels, GFR  
- ProteinInUrine  
- SerumElectrolytesSodium, SerumElectrolytesPotassium  
- HemoglobinLevels  
- CholesterolTotal, CholesterolHDL  
- Diuretics  
- Edema, NauseaVomiting, MuscleCramps, Itching  

---

## Data Cleaning
- Duplicate removal: Removed using `df.drop_duplicates()` to avoid bias from repeated rows.  
- Irrelevant columns: Dropped non-medical identifiers such as `PatientID` or names.  

---

## Data Preprocessing
- Feature and label separation:  
  ```python
  X = df_numeric.drop(columns='Diagnosis')
  y = df_numeric['Diagnosis']
Train-test-validation split: 70% training, 20% testing, 10% validation

Handling class imbalance: Applied SMOTE to balance CKD and non-CKD cases

Handling missing values: Replaced/processed null values to maintain data consistency

Encoding categorical variables: Converted categorical values into numeric representations

Normalization: Standardized numerical attributes such as cholesterol, blood sugar, and blood pressure

