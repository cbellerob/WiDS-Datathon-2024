# WiDS Datathon++ 2024 University Challenge

## Overview

Our team actively engaged in the 2024 WiDS Datathon as part of Chapman University's CPSC-298 course, where we predicted
predict time to treatment of women patients who are diagnosed with metastatic triple-negative breast cancer.   

[WiDS Datathon++ competititon](https://www.kaggle.com/competitions/widsdatathon2024-university/overview)
<br></br>

## Team Members
- [Paige Caskey]()
- [Tiffany Le]()
- [Caroline Robinson](https://github.com/cbellerob)

## Table of Contents
- [Introduction](https://github.com/cbellerob/WiDS-Datathon-2024#introduction)
- [Methods](https://github.com/cbellerob/WiDS-Datathon-2024#methods)
- [Results](https://github.com/cbellerob/WiDS-Datathon-2024#results)
- [Discussion](https://github.com/cbellerob/WiDS-Datathon-2024#discussion)
- [Future Work](https://github.com/cbellerob/WiDS-Datathon-2024#future-work)
- [Acknowledgements](https://github.com/cbellerob/WiDS-Datathon-2024#acknowledgements)

## Introduction
Our model aims to accurately predict the time to treatment of patients diagnosed with metastatic breast cancer, specifically how many days to treatment. The data provided by WiDS included individual and demographic information, including socio-economic impacts and diagnosis details. This model can be useful because it helps identify and prevent delays in treatment, especially for individuals who are already at a disadvantage in the healthcare system. Overall, the model can impact healthcare policy, resource allocation, and overall equity in the healthcare system.

## Methods
#### Data Preparation
Preparation began with dropping all missing values from the predictors we included in our model. 
We decided not to fill these in, as there wouldn’t be a significant loss in data. 
However, imputation was still performed for the predictors with a high quantity of missing values, the most important being patient_race. 
This was handled by imputing patient_race based on the most populous race in the individual's region (given the demographic data provided). 
Finally, we assumed patients with missing values for payment_type were individuals without health insurance, so these values were imputed with “None.” Feature engineering was performed, too, on metastatic_first_treatment_type. We transformed this feature into binary values, where 1 indicated Antineoplastics and 0 for the others.

#### CatBoost Model
Input data/predictors and the target value were assigned to X_train and y_train, respectively. 
Preprocessing was performed by standardizing the continuous predictors and one-hot encoding the categorical predictors.
We constructed a predictive model using CatBoost, selecting relevant parameters to optimize performance, and then put it into a pipeline with the preprocessing.
The pipeline was fit to the training data and then applied to the testing data. Parameters, including iterations and learning rate, were adjusted to prevent overfitting and lower the error rate. Model performance was evaluated using Root Mean Squared Error (RMSE), the designated metric for the datathon.

## Results

## Discussion

## Future Work
We are committed to improving the performance of our model throughout the remaining duration of the 2024 WiDS Datathon. This includes, but not limited to,
refining our current CatBoost model and further exploring other approaches, such as XGBoost or an ensemble of these models.

## Acknowledgements
We would like to acknowledge [Dr. Chelsea Parlett Pelleriti](https://github.com/cmparlettpelleriti), our professor for this course, for her valuable guidance throughout this challenge. 
Dr. Parlett provided thorough class lectures, relevant resources, and constructive feedback, which played a critical role in shaping and advancing the success of our project for the
Kaggle Competition.
