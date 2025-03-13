# Oral Cancer Prediction: Individual and Health Expenditure Analysis
# Motivation
Oral cancer is a severe disease that, if diagnosed early, significantly increases survival rates. However, late-stage diagnosis leads to higher treatment costs and mortality rates. While individual risk factors such as tobacco use, alcohol consumption, and genetic predisposition play a crucial role in oral cancer development, healthcare accessibility and government spending on health services may also influence early detection rates.
This project aims to:
1.	Develop a machine learning model to predict oral cancer diagnosis at the individual level.
2.	Analyze the relationship between national healthcare expenditure and cancer detection rates.
By combining individual health data with country-level health spending, we aim to gain deeper insights into both personal and systemic factors affecting oral cancer diagnosis.
________________________________________
# Dataset
This project will integrate two datasets:
- First Dataset (Individual-Level Data) – Kaggle 
  -	Demographics: Age, Gender, Country
  -	Lifestyle & Risk Factors: Tobacco Use, Alcohol Consumption, HPV Infection, Betel Quid Use,  Chronic Sun Exposure, Poor Oral Hygiene, Diet Quality, Family History of Cancer, Compromised Immune System
  -	Early Symptoms: Oral Lesions, Unexplained Bleeding, Difficulty Swallowing, White or Red Patches in Mouth
  -	Tumor Information: Tumor Size (cm), Cancer Stage
  -	Target Variable: Oral Cancer Diagnosis (Yes/No)
- Second Dataset (Country-Level Data) – World Bank Group
  -	Health Expenditure per Capita (Annual healthcare spending per person in USD)  

  **Data Processing Adjustments:**
  - The "Country" feature in the primary dataset will be used to map health expenditure data to individual records.
  -	To prevent data leakage, treatment-related features (e.g., treatment type, survival rate, cost of treatment) and other unrelated data will be excluded.
________________________________________
# Methodology
The project will consist of two main analyses:
- **Individual-Level Analysis: Machine Learning Model for Cancer Prediction**
  -	Data Preprocessing 
    -	Remove unnecessary columns such as ID and treatment-related data.
    -	Convert categorical variables using Label Encoding and One-Hot Encoding.
    -	Handle missing values through imputation.
  -	Exploratory Data Analysis (EDA) 
    -	Analyze feature distributions among cancer and non-cancer cases.
    -	Identify key risk factors using feature importance techniques.
- **Country-Level Analysis: Health Expenditure and Early Diagnosis**
  -	Data Integration 
    -	Merge World Bank's Health Expenditure per Capita data with individual records based on country.
  -	Statistical Analysis 
    -	Perform correlation analysis to examine the relationship between health spending and early cancer diagnosis rates.
________________________________________
# Expected Outcomes
-	A machine learning model capable of predicting oral cancer risk based on lifestyle and medical history.
-	A statistical analysis of how national healthcare expenditure affects early diagnosis rates.
________________________________________
# Conclusion
By integrating individual health risk analysis with country-level healthcare spending, this study aims to provide a comprehensive understanding of oral cancer diagnosis patterns. This dual approach can enhance early detection efforts and support healthcare policy decisions to improve cancer screening and prevention strategies.
