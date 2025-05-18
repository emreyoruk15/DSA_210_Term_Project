# Oral Cancer Prediction: Individual and Health Expenditure Analysis
# Motivation
Oral cancer is a severe disease that, if diagnosed early, significantly increases survival rates. However, late-stage diagnosis leads to higher treatment costs and mortality rates. While individual risk factors such as tobacco use, alcohol consumption, and genetic predisposition play a crucial role in oral cancer development, healthcare accessibility and government spending on health services may also influence early detection rates.
This project aims to:
1.	Develop a machine learning model to predict oral cancer diagnosis at the individual level.
2.	Analyze the relationship between national healthcare expenditure and early cancer detection rates.
3.	Build a predictive model to estimate 5-year survival rates of diagnosed oral cancer patients.
By combining individual health data with country-level health spending, we aim to gain deeper insights into both personal and systemic factors affecting oral cancer diagnosis.
________________________________________
# Dataset
This project will integrate two datasets:
- First Dataset (Individual-Level Data) – Kaggle 
  -	Demographics: Age, Gender, Country
  -	Lifestyle & Risk Factors: Tobacco Use, Alcohol Consumption, HPV Infection, Betel Quid Use,  Chronic Sun Exposure, Poor Oral Hygiene, Diet Quality, Family History of Cancer, Compromised Immune System
  -	Early Symptoms: Oral Lesions, Unexplained Bleeding, Difficulty Swallowing, White or Red Patches in Mouth
  -	Tumor Information: Tumor Size (cm), Cancer Stage
  -	Treatment: Treatment Type
  -	Target Variable: Oral Cancer Diagnosis (Yes/No), Surival Rate
- Second Dataset (Country-Level Data) – World Bank Group
  -	Health Expenditure per Capita (Annual healthcare spending per person in USD)  

  **Data Processing Adjustments:**
  - The "Country" feature in the primary dataset will be used to map health expenditure data to individual records.
  -	To prevent data leakage, treatment-related features (e.g., economic burden, cost of treatment) and other unrelated data will be excluded.
________________________________________
# Methodology
The project will consist of three main analyses:
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
- **Survival Rate Prediction**
  - Survival Rate will be predicted based on  age, gender, tumor size, cancer stage, treatment type and, health expenditure taken from the second dataset
________________________________________
# Expected Outcomes
-	A machine learning model capable of predicting oral cancer risk based on lifestyle and medical history.
-	A statistical analysis of how national healthcare expenditure affects early diagnosis rates.
-	A machine learning model that predicts survival rate.
________________________________________
# Data Analysis and Hypothesis Testing
## Importance of Health Expenditure for Early Diagnoses
- **Null Hypothesis:**  There is no significant difference in early diagnosis rates between high and low health expenditure countries.
- **Alternative Hypothesis:** There is a significant difference in early diagnosis rates between high and low health expenditure countries.

T test is applied and the following results are found:
T-statistic: 2.589,
P-value: 0.021

Reject the null hypothesis: There is a significant difference in early diagnosis rates between high and low health expenditure countries.

![99291a57-621c-465d-82fe-cdba1c1a5af7](https://github.com/user-attachments/assets/255d5281-3c8c-4808-b02e-dafccae49311)
## Effects on Survival Rate
### Early Diagnosis
- **Null Hypothesis:** There is no significant difference in survival rates between early and late diagnosis groups.
- **Alternative Hypothesis:** There is a significant difference in survival rates between early and late diagnosis groups.

T test is applied and the following results are found:
T-statistic: 2.966
P-value: 0.003

Reject the null hypothesis: There is a significant difference in survival rates between early and late diagnosis groups.
![3f0ee2f1-78a4-470d-a963-36610e03bfda](https://github.com/user-attachments/assets/9ff47f7a-a7c2-4dec-972c-ca93d10fc988)

### Gender
- **Null Hypothesis:** No significant difference in survival rates between genders.
- **Alternative Hypothesis:** Significant difference in survival rates between genders.
  
T test is applied and the following results are found:
T-statistic: 2.966
P-value: 0.003

Fail to reject the null hypothesis: No significant difference in survival rates between genders.
![a9ff3936-8d62-44bb-b644-bb5dda05211b](https://github.com/user-attachments/assets/05843561-3dcd-4069-9267-92753590104c)

### Treatment Type
- **Null Hypothesis:** No significant difference among treatment types.
- **Alternative Hypothesis:** Survival rates significantly differ across treatment types.

ANOVA is applied and the following results are found:
F-statistic: 0.4491, p-value: 0.7731

Fail to reject the null hypothesis: No significant difference among treatment types.
![85cd840f-fc1d-4fcc-adef-a7853d99e4b8](https://github.com/user-attachments/assets/0a5ce905-dcf0-45c8-9de3-8bcc089cbe85)

### Cancer Stage
- **Null Hypothesis:** No significant difference in survival rate among cancer stages.
- **Alternative Hypothesis:** Survival rates differ significantly between cancer stages.

ANOVA is applied and the following results are found:
F-statistic: 354344.6336, p-value: 0.0000

Reject the null hypothesis: Survival rates differ significantly between cancer stages.
![6b0639f6-cc4d-4953-80b0-2933f54265f6](https://github.com/user-attachments/assets/f81a8aeb-fb66-4245-87f0-e7c58036c90a)

### Age
- **Null Hypothesis:** No significant correlation found between age and survival rate.
- **Alternative Hypothesis:** Significant correlation found between age and survival rate.

Pearson correlation calculated and the following results are found:
Pearson correlation between Age and Survival Rate (Cancer Patients Only):
Correlation: -0.0015, p-value: 0.7637

Fail to reject the null hypothesis: No significant correlation found between Age and survival rate.

![039d0346-bb8d-4b15-8cab-f079b4694d40](https://github.com/user-attachments/assets/d0e264d1-b226-42c3-9f90-1d6ab36f4940)

### Tumor Size
- **Null Hypothesis:** No significant correlation found between tumor size and survival rate.
- **Alternative Hypothesis:** Significant correlation found between tumor size and survival rate.

Pearson correlation calculated and the following results are found:
Pearson correlation between Tumor Size (cm) and Survival Rate (Cancer Patients Only):
Correlation: 0.0036, p-value: 0.4626

Fail to reject the null hypothesis: No significant correlation found between Tumor Size (cm) and survival rate.

![04a1aa0a-2378-47c4-bcdd-65fcab85494e](https://github.com/user-attachments/assets/c91f5a67-cc56-4bd6-b8b7-4c4f282757de)

### Health Expenditure
- **Null Hypothesis:** No significant correlation found between health expenditure and survival rate.
- **Alternative Hypothesis:** Significant correlation found between health expenditure and survival rate.

Pearson correlation calculated and the following results are found:
Pearson correlation between Health Expenditure and Survival Rate (Cancer Patients Only):
Correlation: 0.0055, p-value: 0.2576

Fail to reject the null hypothesis: No significant correlation found between Health Expenditure and survival rate.
![a928051d-d97d-4bc8-bbf3-b9519c5e1994](https://github.com/user-attachments/assets/0a633f81-8227-4171-8c5e-8750c8af7876)

## Effects on Oral Cancer
### Tobacco Use
- **Null Hypothesis:** There is no significant association between tobacco use and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between tobacco use and Oral Cancer.

Performed Chi-Squared test and the following results are found:
Chi-squared statistic: 0.296
P-value: 0.586

Fail to reject the null hypothesis:
There is no significant association between Tobacco Use and Oral Cancer.
![817d61f9-fe6f-48b3-a521-87f51bd88947](https://github.com/user-attachments/assets/1ef42d4c-8790-48ac-91a3-b79e54c35a59)


________________________________________
# Conclusion
By integrating individual health risk analysis with country-level healthcare spending, this study aims to provide a comprehensive understanding of oral cancer diagnosis patterns. This dual approach can enhance early detection efforts and support healthcare policy decisions to improve cancer screening and prevention strategies.
