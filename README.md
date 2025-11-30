# My-Heathcare-Project

**Name:** Haniben Patel
**Student ID:** 501345072
**Supervisor Name:** Tamer Abdou

## Project Overview 

This project focuses on analyzing a healthcare dataset to uncover patterns, trends, and insights that can inform better decision-making. The Analysis involves:

- **1.Data Analysis Section:**
  Summerrizing key dataset features using descriptive statistics and visualization, hightlighting    patterns, trends, and outliers.
  
- **2.Data preparation Section:**
  Cleaning, preprocessing, transformationg, and preparing data for modeling.

- **3.Model Evaluation Section:**
  Implementing machine learning models, evaluating their performance using metrics such as precision, recall, and F2-score, and discussing findings.

--- 

## Repository Contents:

- 'data/' -> Contains the healthcare dataset files.
- 'notebooks/' -> Google Colab notebooks with code for analysis, preprocessing, and modeling.
- 'sscripts/' -> python scripts for reproducible data analysis and visualization.
- 'images/' -> sample plots and visualizations from analysis.
- 'README.md/' -> project summary, methodology, and repository documantation.

---

## Key Tools and Libraries:

- python : pandas, numpy, matplotlib, seaborn, scikit-learn
- Google colab for developmeny and exceution

--- 

## Sample Visualizations:

some Examples of the analysis performed in this project:

### 1. Distribution of Patients by Age
![Age Distribution]

### 2. Correlation Heatmap of Feature
![Correlation Heatmap]

### 3. Boxplot Admission Type by Billing Amount
![AdmissionType by Billing Amount]

## Step-by-step Methodology

This project follows a structured approach to analyze the healthcare dataset and evaluate models. 

### 1. Data Exploration and Analysis

- Loads the healthcare datset and inspects its structure.
- Computes descriptive statistics such as mean, median, standard deviation, and distribution of    key features.
- Visualizes data using histograms, boxplots, and correlation heatmaos toidentify patterns,        trends, and outliers.

### 2. Data Cleaning and Preparation

- Handles missing values, duplicates, and incosistent entries.
- Encodes categorical variables and scales numerical features.
- Splits data into training and testing sets for modeling.

### 3. Model Development and Evaluation

- Implements multiple machine learning models including Logistic Regression, Random Forest, and    XGBoost.
- Evaluates models using metrics such as precision, recall, F1-score, and accuracy.
- Compares models performance and selects the best model for prediction.

### 4. Visualization and Reporting

- Generates plots and charts to summarize analysis and model performance.
- Provides insights and recommendations based on analysis results.
  
### 5. Scripts for Reproducibility

- Contains standalone python scripts that replicate data cleaning, analysis, and modeling steps.
- Ensures reproducibility without opening notbooks.

### Observations

- XGBoost outperformed other models with the highest F1-score, indicating strong overall
  perforance.
- Random Forest also performed well, showing stability across different metrics.
- Logistic Regression Provides a simple baseline with resonable performance.





### Final Project Report

### 1.	Research Questions and Contribution Section:

Q1. Which patient characteristics (demographic, clinical, and administrative) most strong predict healthcare outcomes such as Admission Type and Billing Amount?
Q2. Which patient-level and clinical features most strongly influence healthcare outcomes such as hospital charges, length of stay, or admission?
Q3. How accurately cam machine learning models predict healthcare outcomes using structured Electronic Health Record like data?
Q4. What associations exits between hospital, doctor, and insurance provider characteristics and billing amounts?
Q5. What demographic or medical condition clusters emerge across age groups and genders?

Main Contributions compared to past research

•	Random Forest and XGBoost are frequently top performers for tabular healthcare data.
•	Age, chronic conditions, lab values, and diagnosis codes are typically strong predictors for cost or admission models.

### 2.	Literature Review and Integration

Align with past Research:        
•	Past studies consistently show that patient age, severity indicators, diagnosis codes, and   procedures are strong predictors of cost and admissions.
• Studies using Random Forest and XGBoost frequently report better performance than linear models, which matches your results where Random Forest and XGBoost had lower errors.

           
Literature review and data analysis
•	Literature supports the idea that healthcare costs and admissions are multifactorial, involving patient, clinical, and administrative variables.
•	This combined evidence suggests that interpretable machine learning is essential for understanding healthcare outcomes.                                                                              
### 3.	Methodology and Study Design Section 
Methodology:

1.	Data preprocessing: 
•   Loaded dataset from Kaggle in Google Colab.
•   Handled missing values using:
    --Median/mean imputation for numerical fields.
    --Mode imputation for categorical values.
•   Encoded categorical features using:
    --One-Hot Encoding (for nominal categories).
  	--Ordinal Encoding (where meaningful order existed).
•   Standardized numerical variables using StandardScaler.

### Model Selection:
Three models were tested:
1. Linear Regression – baseline model.
2. Random Forest Regressor – nonlinear tree ensemble.
3. XGBoost Regressor – gradient boosting algorithm.

### Hyperparameter Tuning:
•  Used GridSearchCV and RandomizedSearchCV across all models.
•  Selected best-performing model based on 5-fold cross-validation MAE.

### Evaluation Metrics:
• Regression metrics: MAE, MSE
• Classification metrics: accuracy, precision, recall, F1.
• Model stability: cross-validation scores, performance on unseen subsets.
• Efficiency: training time recorded using Colab's Python timers.

### Training & Testing Process:
• Split dataset into 80% training and 20% testing.
• Trained models on training set and evaluated on test set.
• Performed feature importance extraction using:
   --Permutation importance.
   --Model coefficients (for linear models).


### 4.	Model Evaluation Section

Effectiveness: 

Regression Results (From model runs)

Model                            MAE	         MSE
Linear Regression             12192.29	     14109.04
XGBoost Regressor             12335.20	     14253.74
Random Forest  Regressor      11340.89	     13449.91

Key Conclusions:  Random Forest performed best, showing lowest MAE and MSE.

Efficiency:  
•  Linear Regression: Fastest (<1 sec)
•  Random Forest: Moderate (10–20 sec)
•  XGBoost: Slowest (20–40 sec depending on hyperparameters)

Stability:
•  Random Forest and XGBoost showed consistent cross-validation scores.
•  Linear Regression performed poorly when high multicollinearity existed.
•  SHAP and permutation results were stable across random seeds

### 5.	Findings and Interpretation Section: 

Key Insights
•  Random Forest is the most accurate and stable model for this healthcare dataset.
•  Major predictors (based on SHAP and permutation importance) include:
   Age, Blood glucose level, Cholesterol and other lab measures, Hospital service type,     Diagnosis category

Some operational features had unexpectedly high influence, showing hospital process factors affect outcomes significantly.

Interpretation in Context of Research Questions
Q1. Which features matter most?
   -- Lab results, age, and service type are the top drivers.
Q2. How well can models predict costs/outcomes?
   -- Random Forest achieved strong performance with MAE ≈ 11.5K.
Q3. Do findings align with literature?
   -- Yes, most influential features match prior studies; some operational differences noted.

Practical Implications:
•  Hospitals may improve forecasting by including both patient and service-level variables.
•  Feature importance results can support:
    --Resource planning
    --Billing prediction
    --Patient risk stratification

### 6. Limitations and Ethical Considerations Section
Limitations
• Dataset may contain:
  -- Missing values and measurement errors
  -- Simplified or synthetic attributes
  -- Limited diversity across patient groups
• Linear models suffered from multicollinearity.
• No deep learning techniques due to dataset size and project scope.

Ethical Considerations
• Bias: Some features may reflect socioeconomic or demographic bias.
• Data Privacy: Healthcare data requires strict HIPAA/PHIPA-compliant storage.
• Interpretability: Decisions based solely on models may lead to unfair treatment without clinical oversight.
      






  

