# Credit Risk Prediction Project

## Overview
This repository contains code for a Credit Risk Prediction project that aims to assess and predict the creditworthiness of applicants. The project utlizes a dataset comprising information about applicant's credit history, personal details, and other relevant features. The primary goal is to build machine learning models capable of predicting whether an applicant is a credit risk.

## Table of Contents
  - Key Features
  - Requirements
  - Installation
  - Usage
  - Project Struture
  - Results
  - Contributing
  - License


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
