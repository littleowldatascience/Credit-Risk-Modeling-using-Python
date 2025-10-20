## Credit Risk Modeling using Machine Learning with Python

## Project Aim

This project explores a consumer lending dataset (Lending Club) to build end-to-end models for:

- **Probability of Default (PD)** – likelihood a borrower will default
- **Loss Given Default (LGD)** – amount likely lost if default occurs
- **Exposure at Default (EAD)** – how much is at risk at the time of default

The models support financial institutions in evaluating borrower risk, improving portfolio performance, and aligning with regulatory best practices.

## Key Insights

- **Income vs. PD**: Higher incomes are associated with lower Probability of Default (PD)
- **Debt-to-Income Ratio (DTI)**: A strong predictor of creditworthiness
- **Data Skewness**: Required log transformations for certain numeric features
- **Missing Values**: Imputed using correlated variables to improve accuracy

Project Structure

├── datasets

│ ├── loan_data_2007_2014.csv # Raw Lending Club data

│ ├── loan_data_2007_2014_preprocessed.csv # Cleaned dataset

│ ├── df_scorecard.csv # Contains coefficients for the scorecard

├── Models

│ ├── PD Model

│ │ ├── pd_model.sav # Saved model for Probability of Default

│ ├── LGD

│ │ ├── lgd_model_stage_1.sav # Stage 1 model for Loss Given Default

│ │ ├── lgd_model_stage_2.sav # Stage 2 model for Loss Given Default

├── Notebooks

│ ├── Step_1) Credit Risk Modeling_General Preprocessing.ipynb # Exploratory Data Analysis and general preprocessing

│ ├── Step_2) PD model Data Preparation.ipynb # Data preparation specifically for PD model

│ ├── Step_3) PD model Estimation.ipynb # PD model estimation and tuning

│ ├── Step_4) Credit Risk Modeling and Scorecard Development for PD.ipynb # PD model training and scorecard creation

│ ├── Step_5) Credit Risk Model Monitoring and PSI Analysis.ipynb # Model monitoring and stability analysis using PSI

│ ├── Step_6) Expected Loss Estimation and Credit Risk Analysis.ipynb # Modeling LGD and EAD, followed by expected loss calculation

## Dataset Access

Full `.csv` files and saved models could be found with this link [Google Drive Dataset Folder](https://drive.google.com/drive/folders/195BjYLAjVUeORCfzkNj0VDmFDXEKZ31t?usp=sharing) due to GitHub storage limits.

## Dataset Overview

The dataset contains information on over 800,000 consumer loans issued from 2007 to 2015 by Lending Club, a large US peer-to-peer lending company. We use a version that includes various borrower attributes and loan characteristics. This dataset was previously available on Kaggle. An alternative Lending Club dataset can be explored here: [Kaggle Lending Club Dataset](https://www.kaggle.com/code/ianolmstead/credit-risk/input?select=loan_data_2007_2014.csv).
Modeling Approach

    PD Model: Logistic Regression was used to predict the Probability of Default, evaluated using metrics like Area Under the Curve (AUC) and F1 score.
    LGD Model: A two-stage approach involving Logistic Regression for the initial stage and Linear Regression for the second stage, evaluated using Mean Absolute Error (MAE) for model accuracy.
    EAD Model: Linear Regression with R-squared as the evaluation metric is used to estimate the Exposure at Default.

## Tools and Libraries

The project utilizes the following libraries and tools:

    pandas for data loading, cleaning, and transformation
    scikit-learn for building and training the logistic and linear regression models
    plotly for interactive visualizations to uncover patterns and insights in the data
    Flask for creating a simple web application to deploy the model and demonstrate real-time predictions

## Additional Libraries

    numpy for numerical operations
    matplotlib for supplementary plotting
    scipy for statistical functions and calculations

## Score Card (FICO Score 300-850)

The project includes the development of a scorecard aligned with the FICO scoring system. This scorecard provides an intuitive and standardized risk assessment for each loan, making it easier for lenders to interpret the creditworthiness of borrowers.
Credits
This project is based on knowledge gained from the following course: [Credit Risk Modeling in Python](https://365datascience.com/courses/credit-risk-modeling-in-python/).
