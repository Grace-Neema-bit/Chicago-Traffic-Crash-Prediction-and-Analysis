# Chicago-car-Crash-Prediction-and-Analysis
![view-chicago-traffic-rush-hour-afternoon-282786158](https://github.com/user-attachments/assets/6a30ec49-1dba-40e0-8762-c9bec42dd6dc)

## BUSINESS UNDERSTANDING
## Problem Statement
Traffic accidents are a major concern in Chicago. Understanding the conditions that lead to severe crashes will help the Vehicle safety board.
This project aims to build a classification model that predicts whether a car crash will result in injuries based on environmental factors or other factors. The insights from this model will help identify high risk conditions and implement preventive measures to imrove road safety.

## Stakeholders
- Vehicle safety board
   - Responsible for road safety
   - Implement safety programs
   - They will use this model to identify high risk driving conditions and issue weather related alerts 
- City of Chicago
    - Responsible for infrastructure

## Key Questions
1. What factors contribute to most crashes?
2. Under what conditions are crashes most likely to result in injuries?
3. Can we predict whether a crash will result in injuries based on environmental conditions?
4. Can we predict the primary contributory cause of accidents?
## Data Understanding
The dataset we are using has been obtained from kaggle, it contains car crashes in chicago from 2019 to 2022. Its particulary useful because it includes car crash variables and environmental factors that influence crash outcomes. It allows us to analyze patterns in traffic accidents.

------------------------------------------------------------------------

## Project Workflow

The project follows the **standard data science workflow:**

1.  Business Understanding
The aim is to help stakeholders such as city planners and vehicle safety authorities identify patterns in crashes and implement strategies to reduce accidents.

2.  Data Understanding

* Loaded dataset and examined structure using:

  * `df.shape`, `df.info()`, `df.describe()`
* Checked missing values and class distribution
3.  Data Preparation
4.  Modeling
5.  Evaluation
6.  Conclusion and Recommendations

------------------------------------------------------------------------

## Data Preparation

Several preprocessing steps were performed before training the models:

-   Cleaning missing values
-   Mapping injury values to numeric format
-   Creating a binary target variable (contributory_cause`)
-   Feature engineering from crash dates
-   One-hot encoding categorical variables
-   Selecting relevant model features
-   Standardizing numerical variables using StandardScaler

Target Variable:THis is a multiple classification model so we used the 

`contributory_cause` as our target variable
Due to class imbalance, the number of categories was reduced to the most frequent classes, with others grouped into an **“Other”** category.

------------------------------------------------------------------------

 Exploratory Data Analysis (EDA)

Visualizations were used to understand patterns


## Feature Selection

The following features were selected for modeling:

windspeed                
winddir                  
pressure                 
visibility               
cloudcover               
moonphase                
lattitude                
days_temp                
num_vehicles_in_crash    
longitude                
days_feelslike           
dew                      
precip                   
precipprob               
contributory_cause       
dtype: int64

These features represent environmental conditions and crash
characteristics that may influence injury outcomes.

------------------------------------------------------------------------

## Models Used

Two machine learning models were used in this project:

### 1. Logistic Regression (Baseline Model)

Logistic Regression was used as the baseline classifier. It provides a
simple and interpretable model for binary classification problems.

### 2. Random forest
Random Forest is the best because it solves two major problems:

Prevents Overfitting: A single tree might "memorize" your training data, leading to 100% accuracy on old data but 0% on new data. By averaging many trees, the Random Forest cancels out individual errors.

Handles "Messy" Data: It doesn't care if your weather data hasn't been scaled or if there are non-linear relationships (e.g., crashes don't just increase as it gets colder; they spike specifically at the freezing point of 0°C).

------------------------------------------------------------------------
## Process
-   Train_test split of 80/20
-   Feature scaling
-   Cross_validation
## Model Evaluation
  
Models were evaluated using:

-   Accuracy Score
-   Confusion Matrix
-   ROC_AUC
-   Classification Report (Precision, Recall, F1-score)

* **Pipelines** for cleaner workflow
* **Ensemble (Voting Classifier)** to combine models


These metrics help measure how well the models predict injury outcomes.

------------------------------------------------------------------------
![alt text](image.png)
The performance of the models was compared using accuracy scores.

The comparison helps determine which model performs better in predicting
injury-related crashes.

------------------------------------------------------------------------

## Key Insights

The analysis helps identify:

-   Environmental conditions associated with higher injury risk
-   Crash patterns linked to severe accidents
-   Predictive indicators of injury-causing crashes

These insights can help authorities implement preventative measures to improve road safety.

### Feature Importance

* Extracted from Random Forest model
* Identified key drivers of crash causes such as:

  * Road conditions
  * Weather conditions
  * Traffic control devices

## Future Improvements

* Apply advanced models (e.g., XGBoost, Gradient Boosting)
* Improve feature engineering (time-based, location clustering)
* Use hyperparameter tuning for better performance
* Deploy model as a real-world application

------------------------------------------------------------------------

## Recommendations
-   Improve intersections -Use roundabouts or better signaling

-   Target high-risk zones -Deploy speed cameras and patrols

-   Weather alerts - Notify drivers during risky conditions 

-   Emergency response system - Use model predictions to prioritize dispatch

## Colclusion

While a standard model prioritizes on accuracy, we optimized for recall. The model reveals thst the more the cars at in interserctions the higher the impact of accidents.
The city should focus on multi vehicle intersections within the high risk lattitude and the allocate resources where they will have immediate impact on saving lives


---




