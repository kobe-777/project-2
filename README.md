# Credit Risk Prediction Project

## Overview
This repository contains code for a Credit Risk Prediction project that aims to assess and predict the creditworthiness of applicants. The project utlizes a dataset comprising information about applicant's credit history, personal details, and other relevant features. The primary goal is to build machine learning models capable of predicting whether an applicant is a credit risk.

## Table of Contents
  - Key Features
  - Requirements
  - Project Struture
  - License
  - Past Due 30-59 Days and Customer Status Distribution
  - Data Preprocessing
  - 'OCCUPATION_TYPE' Random Forest Classifier
  - Categorical Variables Distribution
  - Numerical Variables Distribution
  - Scatter Plot Analysis
  - Logistic Regression Model
  - Random Forest Classifier
  - XGBoost Model
  - Multi-Layer Perceptron Model (MLP)


## Key Features
1. ### Data Preprocessing and Feature Engineering:
   This includes the initial setps of loading and cleaning data. It performs feature engineering, handling missing values, and transform the dataset for further analysis.

2. ### Exploratory Data Analysis (EDA):
   It explores the distribution of past due days, customer status, and other relevant factors. Visualization such as count plots and heatmaps are used to gain insights into the dataset.

3. ### Occupation Type Prediction:
   It focuses on predicting missing values in the 'OCCUPATION_TYPE' column using a Random Forest Classifier. Categorical variables are encoded, and the model is trained to fill Nan values.

4. ### Credit Risk Modeling:
   It builds machine learning models to predict credit risk. It covers data preprocessing, one-hot encoding, feature scaling, and the application of the Synthetic Minority Over-sampling Technique (SMOTE) to handle class inbalance. This includes the training and evalution of Logistic Regression and Decision Tree models.

## Requirements
- Python 3.x
- Required Python package

## Past Due 30-59 Days and Customer Status Distribution
  In this section, we execute dual-subplot figure to analyze credit related data. It visualizes the distribution of customers based on past due days (30-59 days) and their credit status. Clear count labels offer quick insights into the dataset. Potential findings include identifying credit risk areas and asessing overall credtiworthiness.
![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Past%2030%20Days.png?raw=true) 

## Past Due 60-89 Days and Customer Status Distribution
In this section, we analyze credit data, assigning 'Credit Risky' or 'Creditworthy' status based on days past due 60-89 days. The visualizations display distributions, offering insgihts into credit risk concentration and customer statuses.
![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Past%2060%20Days.png?raw=true)

## Data Preprocessing:
- The target variable 'customer_status' has been defined based on the number of days past due 60 days and 30 days. This variable represent whether a customer is past due on payments.
- Merged 'credit_grouped' DataFrame with 'application_df' using index.
- Demographic Features: The 'DAYS_BIRTH' and 'DAYS_EMPLOYED' have been converted to columns 'AGE' and 'YEAR_EMPLOYED'.
- Handling Missing Values: There are missing values in the "OCCUPATION_TYPE" column, which might need further consideration. The most common occupation type could be imputed or a sepatate category  for missing values could be created.
- Dropping Unnecessary Columns such as "FLAG_MOBIL","FLAG_WORK_PHONE","FLAG_PHONE", and "FLAG_EMAIL" have been dropped as they are considered unnecessary.

## 'OCCUPATION_TYPE' Random Forest Classifier:
  The goal was to address the issue of missing values in the 'OCCUPATION_TYPE' column by training a machine learning model (Random Forest Classifier) and filling the missing values.
  ### Model Performance:
  ### Classification Report:
   - Precision, recall, and F1-score were provided for each class in 'OCCUPATION_TYPE". It is indicating a robust performance in predicting both positive and negative instances.
   - The F1-score, which considers both precision and recall, reflected strong model performance, especially in classes with high number of samples.
   - The overall accuracy of 0.9178 suggests the model's ability to correctly predict "OCCUPATION_TYPE" for the test set.
    
The imputation process successfully addressed the issue of missing values in the "OCCUPATION_TYPE" column. The imputed values were obtained using Random Forest Classifier trained on the available data. The resulting dataset is now more complete, allowing for more robust analyses and modeling. 

  ### Correlation Analysis:
  The goal of this analysis is to examine to correlation between selected features in the dataset, including key numerical and one-hot encoded categorical variables.
  - Categorical variables (CODE_GENDER, FLAG_OWN_CAR, FLAG_OWN_CAR, FLAG_OWN_REALTY) were one-hot encoded to convert them into numerical form for correlation analysis.
  - A subset of key features was selected for correlation analysis. These features include 'customer_status', numerical variables and one-hot encoded variables.
  - Postivie correlations are observed between 'FLAG_OWN_CAR_Y' and 'CODE_GENDER_M', as well as between 'FLAG_OWN_REALTY_Y and 'CODE-GENDER_F'. These relationship may suggest some associations between car ownership,       
    gender, and realty ownership
    
    ![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Correlation%20Analysis.png?raw=True)

## Categorical Variables Distribution:
The dataset includes a mix of numerical and categorical variables. Notable categorical variables such as "CODE_GENDER","FLAG_OWN_CAR", and "FLAG_OWN_REALTY" provide insights into demographic and lifestyle characterstics.
-  Gender Distribution: This indicates a balanced representation of genders in the dataset. This gender balance is valuable for ensuring diversity in the analysis and model traning.
-  Car Ownership Distribution: It reveals that a substantial number of individuals in the dataset do not own car.
-  Real Estate Ownership: The significant proportion of individuals owning real estate suggests a financially stable or eatablished segment in the dataset. This information can be valuable for predicting creditworthiness and assessing financial health.

  Understanding the distribution of categorical variables provides a foundation for more advaned analyses and model building. These insights contribute to informed decision_making and improve the interoretability of models, especially in the context of creditworthiness prediction and financial assessment.

  ![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Gender%2C%20Car%20and%20Real%20Estate%20Distribution.png?raw=true)

## Numerical Variables Distribution:
  The distribution of two eky numerical variables: 'Age' and 'Total Income'(AMT_INCOME_TOTAL). These variables offers insights into the age demographics and income distribution within dataset.
  ### Age Distribution:
  - The dataset exhibits a balanced distribution of ages, with a concentration in the 30-60 age range.
  ### Total Income Distribution:
  The total income distribution is right skewed, indicating that a majority of individuals have lower to moderate incomes. However, the presence of higher income outliers suggests a degree of income display within the dataset.
  Understanding the distribution of numerical variables provides valuable insight into the demographics and financial charaterstics of the dataset.

  ![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Age%2C%20Total%20Income%20Distribution.png?raw=true)

## Scatter Plot Analysis:
  The scatter plot provides a visual representation of the relationship between age and total income. While there is no clear linear treand, identifying clusters and addressing outliers are critical steps for refining analyses and build accurate predictive models.
 
![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Relationship%20between%20Age%20and%20Total%20Income.png?raw=true)

## Logistic Regression Model:
  ### SMOTE:
  - The 'CNT_CHILDREN' column, being a subset of 'CNT_FAM_MEMBERS', has been dropped for simplicity.
  - The 'CNT_FAM_MEMBERS' column has been simplified, grouping counts of 4 or more into a single category.
  - Categorical column have been one-hot encoded, and numerical column have been scaled using a 'ColumnTransformer'.
  - The target variable(customer_status) and feature set have been prepared for model training.
  - Synthetic Minority Over-sampling Techique (SMOTE) has been applied to address calss imbalance by oversampling the minority class.
  - Logistic Regression has been chosen as the classification model.
  - The model has been trained on the SMOTE data and evaluated on the test set.
  - The classification report and confusion matrix provide insight into model performance.
  - Precision for calss 0 is high 0.99, indicating a low flase positive rate. However, for class 1 is low 0.02, suggesting a high false positive rate.
  - Recall for calss 0 is low 0.57, indicating that the model misses a significant number of actual positives.
  - Recall for class 1 is relatively higher 0.60, suggesting better identification of actual postives.

    The data for classification, addressing class imbalance through SMOTE and RUS (Random Under-Sampling) techniques, and training a Logistic Regression model. However, the model's performance revealed a tradeoff between precision and recall, with a high precision for class 0 but low recall for both classes The overall accuracy is 0.57, indicating that the model is not performing well in terms of correctly predicting both classes.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Log%20Regression%20Confusion%20Matrix%20SMOTE.png?raw=true)

  ### Undersampled
  The logistic regression model trained on the undersampled data results:
  - Precision for the majority class 0 was high at 0.99, but it was notably lower for the class 1 at 0.02.
  - recall for the class 0 was 0.55, indicating a portion of true positives was missed.
  - recall for the class 1 was 0.60,reflecting an improvement compared to the SMOTE model.
  - The F1-score, considering both precision and recall,showed better balance for the class 1 than the SMOTE model.
  - The overall accuracy was 0.55, highlighting the trade-off between the classes.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Log%20Regression%20Confusion%20Matrix%20Undersampled.png?raw=true)

## Random Forest Classifier:
  ### SMOTE:
 The Random Forest model trained on the SMOTE (Synthetic Minority Over-sampling Technique) data exhibits a strong performance in prediciting the class 0,achieving high precision and recall, indicating few false postivies and false negatives. However, the model faces challenges in predicting the minority class 1. Despite achieving relatively high precision 0.36, there is a notable trade-off with recall 0.29, indicating a considerable number of false negatives. This suggests that the model struggles to identify instances of the class 1.
 The overall accuracy of 0.98 might be misleading due to the class imbalance, as the model performs exceptionally well on the class 0 but struggle with class 1. the F1-score forthe class 1 is notably lower compared to the class 0, indicating an imbalance in precision and recall.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Random%20Forest%20Class%20SMOTE.png?raw=true)
    
  ### Undersampled:
  The Random Forest model trained on the undersampled data demonstrates improved performance in predicting the class 1 compared to the model trained on the SMOTE data. Although precision for the class 1 remains low 0.03, the recall has substantially increased 0.66, indiacting fewer false negatives. This suggests that the model is now more effective at identifying instances of the class 1, reducing the likelihood of overlooking positive cases.
  The overall accuracy of 0.68 is reflective of a more balanced performance across both classes, as the model successfully captures a higher proportion of the class 1. the F1-score for class 1 has notably improved, signifying a better balance between precision and recall.

  This model trained on undersampled data enhanced performance in identifying instances of the class 1, striking a better balance between precision and recall compared to the model trained on SMOTE data.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/Random%20Forest%20Class%20undersampled.png?raw=true)

## XGBoost Model:
  ### SMOTE:
    The XGBoost model trained on the SMOTE data exhibits robust performance in predicting class 0 with high precision and recall, achieving an accuracy of 0.98. However, its ability to predict class 1 remains limited, witha lower precision and recall of 0.38 and 0.36, respectively.
    While the overall model accuaracy is high, the imbalanced performance on the class 1 suggests the need for further turning or exploration of alternative techniques to enhance the mode's sensitivity to positive instances. The F1-score for the class 1 is 0.37, indicating a moderate balance between precision and recall.
    
    This model demonstrating strong overall accuracy, requires further optimization to address the imbalanced performance on class 1.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/XGBoost%20SMOTE%20.png?raw=true)

  ### Undersampled:
  The XGBoost model trained on the undersampled data demonstrates a notable accuracy of 0.65. Similar to the model trained on the SMOTE data, it excels at correctly classifying instances belong to class 0. However, the performance on class 1 reveals some challenges, with a precision of 0.03 and recall of 0.70. This indicatest that while the model is adpat at minimizing false positives for class 1, it struggles with false negatives, leading to a lower precision.
  The F1-score for class 1 is 0.06, suggesting that there is significant room for imprvement in finding a better balancebetween precision and recall for positive instances.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/XGBoost%20undersampled%20.png?raw=true)

## Multi-Layer Perceptron Model (MLP):
  ### SMOTE:
    The Multi_layer Preceptron (MLP) model trained on the SMOTE data exhibits an impressive accuracy of 0.96, reflecting its proficiency in accurately predicting class 0. However, the performance on class 1 reveals challenges, with a precision of 0.17 and recall 0.41. This suggests that while the model minimizes false positives for class 1, there are considerable negatives, leading to a lower precision.
    The F1-score for class 1 is 0.24, indicating room improvement in achieving a better balance between precision and recall for psotive instances.
    Overall accuracy is 0.96

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/MLP%20SMOTE.png?raw=true)

  ### Undersampled:
  The MLP model trained on the undersampled data displays an overall accuracy of 0.72, showcasing a notable improvment in predicting class 1 compared to the model trained on SMOTE data. The precision for class 1 is 0.03, suggesting that while the model minimizes false positives for positive instances, there is a considerable number of false negatives, impacting overall precision.
  The recall for class 1 is 0.57, indicating that the modelis better at capturing prositve instances,reducing false negatives compared to the SMOTE trained model. The F1-score for class 1 is 0.06, suggesting room for further improvement to achieve a better balance between precision and recall for positive instances.

![alt text](https://github.com/kobe-777/project-2/blob/main/Images/MLP%20under.png?raw=true)
