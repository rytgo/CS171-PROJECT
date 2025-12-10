  
# Predicting Diabetes Risk From Patient Metrics

**Team Members:**

- Andres Aclan
    
- Ryan Tran
    
## **Description of Question and Research Topic**

Diabetes is a chronic disease that is caused when one's blood sugar (glucose) levels cannot be properly regulated. Glucose is the body's main source of energy; With lack of proper management or diagnosis, it can lead to serious health complications down the line. Diabetes can be influenced by one's biological and lifestyle factors. Our project aims to develop and train machine learning models to predict or detect person's likelihood of having (or developing) diabetes. 

**Can lifestyle, health, and demographic features be used to predict diabetes risk?**

## **Project Outline**

1. **Data Preparation:** Search publicly available datasets (Kaggle, UCI), clean, and normalize.
    
2. **Model Building:** Each partner implements and develops a separate model.
    
3. **Evaluation:** Compute accuracy, precision, recall, and ROC AUC
    
4. **Analysis:** Compare and visualize model predictions and evaluate its overall performance

## Installation

**Following course setup:**

**Prerequisites:** Download and install Miniconda
1. Set up a conda environment `conda create --name cs171 python=3.12`
2. Activate `conda activate cs171`
3. Install pertinent packages 
	- conda install numpy
	- conda install matplotlib
	- conda install pytorch
	- conda install torchvision
	- conda install pandas
	- conda install netCDF4
	- conda install scipy
	- conda install scikit-learn
	- conda install jupyter
	- conda install jupyterlab
	- conda install ipykernel
4. Clone the repository and run the data notebook cells.

## **Data Processing Plan**

### **Ryan Tran**

- **Dataset:** [Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
    
- **Content:** 768 patient records with variables such as glucose concentration, blood pressure, insulin, BMI, age, and outcome (0 = no diabetes, 1 = diabetes).
    
- **Cleaning Steps:** Identify physiologically impossible zeros in medical features (e.g., `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI`), convert to NaN, impute, split data

### **Andres Aclan**

- **Dataset:** [Diabetes Health Indicators Dataset](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset)
    
- **Content:** 253,680 survey responses from the CDC's BRFSS2015, featuring 21 health-related features and a target variable with three classes.
    
- **Cleaning Steps:** Clean BRFSS survey responses, remove prediabetic label (`Diabetes_012 == 1`), remap class 2 → 1 (binarize), StandardScaler

## **Project Structure**

- **ryan_data**: Pima Indians dataset, notebook, and processed artifacts.
    - diabetes.csv — raw CSV (~768 rows)
    - PinaNotebook.ipynb — Ryan's preprocessing + Random Forest notebook
    - `ryan_data/models/processed/` — processed train/test CSVs (e.g., X_train_clean.csv, X_test_clean.csv, y_train_clean.csv, y_test_clean.csv)
- **andres_data**: BRFSS 2015 dataset, notebook, and model artifact.
    - diabetes_012_health_indicators_BRFSS2015.csv — raw CSV (~253,680 rows)
    - BRFSS2015.ipynb — Andres' preprocessing + Logistic Regression notebook
    - logreg_pipe.joblib — saved pipeline artifact
	- **`outputs/`**: Result artifacts and exported predictions.
    - outputs/test_predictions.csv

## Project Roles and Models :

- Andres Aclan — BRFSS dataset cleaning, logistic regression pipeline, saved pipeline artifact.
- Ryan Tran — Pima dataset preprocessing (zero→NaN conversion and imputation), Random Forest model development and hyperparameter tuning.

##  **Project Timeline:**

- Week 9-10 → Data exploration and cleaning
    
- Week 11–12 → Model building
    
- Week 13–14 → Evaluation and analysis
    
- Week 15–16 → Presentation and final changes

## Future Work:

- Experiment with additional models (XGBoost, LightGBM) and calibration methods.
- Address class imbalance and apply techniques (SMOTE, class weighting, resampling) and compare its effect.
