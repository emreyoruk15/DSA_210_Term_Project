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
T-statistic: -0.7452  
p-value: 0.4561

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

### Alcohol Consumption
- **Null Hypothesis:** There is no significant association between alcohol consumption and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between alcohol consumption and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.211
P-value: 0.646

Fail to reject the null hypothesis:
There is no significant association between Alcohol Consumption and Oral Cancer
![74dd7a00-5c51-4957-bfce-5935ac3d80a1](https://github.com/user-attachments/assets/4cbb6952-bf80-4917-8454-7fe1d42a0881)

### HPV Infection
- **Null Hypothesis:** There is no significant association between HPV infection and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between HPV infection and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.013
P-value: 0.910

Fail to reject the null hypothesis:
There is no significant association between HPV Infection and Oral Cancer.
![dee94ab1-6ee9-4ac6-a029-f91681ed401b](https://github.com/user-attachments/assets/27036225-8564-4f3d-aeb5-67ae9ce6ea09)

### Betel Quid Use
- **Null Hypothesis:** There is no significant association between Betel Quid Use and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Betel Quid Use and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.212
P-value: 0.645

Fail to reject the null hypothesis:
There is no significant association between Betel Quid Use and Oral Cancer.
![b2c2120c-a82d-4caa-88a5-2409b428464d](https://github.com/user-attachments/assets/daf416a2-a3f5-4524-95e5-1c3742de328d)

### Chronic Sun Exposure
- **Null Hypothesis:** There is no significant association between Chronic Sun Exposure and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Chronic Sun Exposure and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.073
P-value: 0.786

Fail to reject the null hypothesis:
There is no significant association between Chronic Sun Exposure and Oral Cancer.
![1d9b049f-b8e3-4d31-b89d-12f993c54cf0](https://github.com/user-attachments/assets/79149fb9-319f-4d14-b1bc-082b1ddd2b08)

### Poor Oral Hygiene
- **Null Hypothesis:** There is no significant association between Poor Oral Hygiene and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Poor Oral Hygiene and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 2.007
P-value: 0.157

Fail to reject the null hypothesis:
There is no significant association between Poor Oral Hygiene and Oral Cancer.
![dcdd4e5e-61f1-4b0a-b64b-a8f30cdec8ba](https://github.com/user-attachments/assets/ed7174e8-c4c4-4b5b-bb0e-1dbb7ebd0ad3)

### Diet (Fruits & Vegetables Intake)
- **Null Hypothesis:** There is no significant association between Diet (Fruits & Vegetables Intake) and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Diet (Fruits & Vegetables Intake) and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.976
P-value: 0.614

Fail to reject the null hypothesis:
There is no significant association between Diet (Fruits & Vegetables Intake) and Oral Cancer.
![0728f614-81fe-4c2b-a1c4-8594c8411393](https://github.com/user-attachments/assets/1eb9baff-76f1-4e10-8a1a-20ef7dadb7f5)

### Oral Lesions
- **Null Hypothesis:** There is no significant association between Oral Lesions and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Oral Lesions and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.068
P-value: 0.795

Fail to reject the null hypothesis:
There is no significant association between Oral Lesions and Oral Cancer.
![40bb9193-c475-4caf-a35d-3794008fdd96](https://github.com/user-attachments/assets/19729cb3-8768-4603-917c-3dfa78bd228f)

### Unexplained Bleeding
- **Null Hypothesis:** There is no significant association between Unexplained Bleeding and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Unexplained Bleeding and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.004
P-value: 0.952

Fail to reject the null hypothesis:
There is no significant association between Unexplained Bleeding and Oral Cancer.
![c1957ff9-547b-418e-ba0a-9bf82d26075f](https://github.com/user-attachments/assets/069c1b9d-3dad-49c2-b058-1e9f044f9f0f)

### Difficulty Swallowing
- **Null Hypothesis:** There is no significant association between Difficulty Swallowing and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Difficulty Swallowing and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.000
P-value: 1.000

Fail to reject the null hypothesis:
There is no significant association between Difficulty Swallowing and Oral Cancer.
![064864f1-e29e-4273-bb6c-7b329e61e52f](https://github.com/user-attachments/assets/f182b61d-cd91-4293-b9b1-3a73271a2d28)

### White or Red Patches in Mouth
- **Null Hypothesis:** There is no significant association between White or Red Patches in Mouth and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between White or Red Patches in Mouth and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.406
P-value: 0.524

Fail to reject the null hypothesis:
There is no significant association between White or Red Patches in Mouth and Oral Cancer.
![e82b2e59-8307-42e2-aebc-92311dcdbed7](https://github.com/user-attachments/assets/a5ffa7c1-98d0-4935-b106-374f804ff73d)

### Gender
- **Null Hypothesis:** There is no significant association between Gender and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Gender and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 0.010
P-value: 0.920

Fail to reject the null hypothesis:
There is no significant association between Gender and Oral Cancer.
![8057af1d-d314-439d-877a-07d00f1a03cf](https://github.com/user-attachments/assets/d04ee8d0-6bd2-4b7c-bdc7-56c8f2d1b517)

### Family History of Cancer
- **Null Hypothesis:** There is no significant association between Family History of Cancer and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Family History of Cancer and Oral Cancer.

Performed Chi-Squared test and the following results are found:    
Chi-squared statistic: 0.112
P-value: 0.737

Fail to reject the null hypothesis:
There is no significant association between Family History of Cancer and Oral Cancer.
![1a32b1c0-d412-4a03-82f7-5ceab554ac57](https://github.com/user-attachments/assets/306cfd92-73c2-4e7b-afec-d8f16789041e)

### Compromised Immune System
- **Null Hypothesis:** There is no significant association between Compromised Immune System and Oral Cancer.
- **Alternative Hypothesis:** There is a significant association between Compromised Immune System and Oral Cancer.

Performed Chi-Squared test and the following results are found:  
Chi-squared statistic: 2.532
P-value: 0.112

Fail to reject the null hypothesis:
There is no significant association between Compromised Immune System and Oral Cancer.
![ae66d8d6-593e-43d0-9154-4ec3470afc37](https://github.com/user-attachments/assets/1a8dc3fc-384c-4f20-bbf3-f482bfa25649)

### Age
- **Null Hypothesis:** There is no significant difference in age between oral cancer and non-cancer groups.
- **Alternative Hypothesis:** There is a significant difference in age between oral cancer and non-cancer groups.

Performed T-test and the following results are found:  
T-statistic: 0.673
P-value: 0.501

Fail to reject the null hypothesis: There is no significant difference in age between oral cancer and non-cancer groups.
![9df169ed-532b-4d29-9a3c-05c61d795935](https://github.com/user-attachments/assets/733e3259-59e0-4a96-b766-0f26920a7953)
________________________________________
# Machine Learning
## Predicting Survival Rate
For this task, the following features are used to predict the survival rates of oral cancer patients:   
Health Expenditure, Age, Gender, Tumor Size (cm), Cancer Stage, Treatment Type.  

- Categorical variables are encoded.
- Split the data (80% training-20% testing)
- Split the training data for validation (80% training-20% validation)
- Features are scaled with StandartScaler
- Regression model is used to machine learning task (RandomForestRegressor)

### Results  
  --- Train Evaluation ---  
R² Score:  0.994069457233379  
MAE:  1.4808910787919645  
RMSE:  1.8175903075580426  

--- Validation Evaluation ---  
R² Score:  0.9590423099512448  
MAE:  3.9833114983001554  
RMSE:  4.837277960869093  

--- Test Evaluation ---  
R² Score:  0.957393358247016  
MAE:  4.0061089492296  
RMSE:  4.8760741652794755  
![82551ad9-bc2c-48b6-9878-78b370d3273e](https://github.com/user-attachments/assets/36cdef99-34a8-49f0-a11e-56cba362e455)

## Predicting Oral Cancer  
For this task, the following variables are used to predict oral cancer:  
'Age', 'Gender', 'Tobacco Use', 'Alcohol Consumption', 'HPV Infection',
    'Betel Quid Use', 'Chronic Sun Exposure', 'Poor Oral Hygiene',
    'Diet (Fruits & Vegetables Intake)', 'Family History of Cancer',
    'Compromised Immune System', 'Oral Lesions', 'Unexplained Bleeding',
    'Difficulty Swallowing', 'White or Red Patches in Mouth'.  

- Categorical variables are encoded.
- Numerical features are scaled
- Split the data (80% training-20% testing)
- Classifier model is used to predict oral cancer diagnosis

### Results  

![image](https://github.com/user-attachments/assets/86c7d7bb-52d3-4799-b022-cd01bd537214)  

![4e90abcf-6e64-46e2-9a0d-03d18c34cf6a](https://github.com/user-attachments/assets/923afbdc-b20c-4fe4-81d5-e4e37f796a2e)
________________________________________
# Findings
## Importance of Health Expenditure  
In this project, one of the hypothesis was related to the relationship between health expenditure and early diagnosis. The results show that there is a significant difference in early diagnosis rates between high and low health expenditure countries. Additionally, it is known that early diagnosis plays a critical role in cancer treatment. So, it is important to have higher health expenditure to improve early detection rates.  
## Importance of Early Diagnosis
Another hypothesis was related to relation between early diagnosis and survival rate. The results suggest that patients with early diagnosis have a higher survival rate compared to those who were not diagnosed early. Therefore, it is critical to increase the early detection rates.  
## Machine Learning Models
Two model were implemented for two different purpose:  

- **Predicting the survival rates of oral cancer patient.**
This model had a good prediction performance on survival rate with 95.7% test accuracy.
  
- **Predicting the oral cancer patients.**
Unfortunately, model for predicting the oral cancer patients had a bad performance with 50% test accuracy.
________________________________________
# Limitations and Future Work  
## Limitations
- People in the dataset are from certain countries, there are no participants from every country.
- In this project, health expenditures were taken from the general average of the country in which they live, individuals' own health expenditures may be different.
- Ratio of oral cancer patients are much more than real life, which may affect the result of machine learning model.

## Future Work  
- Collect more realistic data (e.g. from health organizations).
- Collect data that includes individuals' own health expenditures.
- Collect data from more countries.
- Creating a new machine learning model by asking experts about the most important features affecting oral cancer.





________________________________________
# Conclusion
By integrating individual health risk analysis with country-level healthcare spending, this study aims to provide a comprehensive understanding of oral cancer diagnosis patterns. This dual approach can enhance early detection efforts and support healthcare policy decisions to improve cancer screening and prevention strategies.  
________________________________________  
# References  
- Oral Cancer Dataset (Kaggle) : https://www.kaggle.com/datasets/ankushpanday2/oral-cancer-prediction-dataset  
- Health Expenditure Dataset (World Bank Group) : https://data.worldbank.org/indicator/SH.XPD.CHEX.PC.CD?most_recent_year_desc=true

