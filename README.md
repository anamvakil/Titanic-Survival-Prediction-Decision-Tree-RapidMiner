# Titanic Survival Prediction (Decision Tree) – RapidMiner

## Overview
This project builds a Decision Tree classifier in RapidMiner to predict Titanic survival (`Survived`) using data cleaning, feature engineering and model evaluation.

<img width="3466" height="1158" alt="image" src="https://github.com/user-attachments/assets/71a4fdc0-f910-4d87-98fb-4d570bfe5427" />

<img width="2973" height="831" alt="image" src="https://github.com/user-attachments/assets/27031bf2-6ed1-480d-869c-aa4501fe690a" />

## Tools
- RapidMiner Studio
- Decision Tree (Gain Ratio)
- Train/Test split + Apply Model + Performance

## Dataset
Titanic dataset (provided in course materials).
> Note: Dataset is not included in this repo if restricted by course policy.
[Titanic_train.csv](https://github.com/user-attachments/files/25329206/Titanic_train.csv)

## Workflow (RapidMiner Process)
### 1) Data Ingestion
- Retrieve / Read CSV into RapidMiner

### 2) Data Cleaning
- Remove Duplicates
- Replace Missing Values (Age)
- Replace Missing Values (Fare)

### 3) Data Preparation
- Numerical to Binominal (Survived)
- Set Role: `Survived` as **label**
- Unify column types

### 4) Feature Engineering
Created new attributes:
- **Relatives** = if(SibSp + Parch == 0, "None", if(SibSp + Parch < 3, "Few", "Many"))
- **AgeGroup** = if(Age < 12, "Child", if(Age < 60, "Adult", "Senior"))
- **FareGroup** = if(Fare < 10, "Low", if(Fare < 30, "Medium", "High"))

### 5) Modelling + Evaluation
- Split Data: 70/30
- Train Decision Tree on training set
- Apply Model on test set
- Performance metrics generated

## Results 
- Accuracy: **75.66%**
- Confusion matrix + precision/recall available in `/screenshots/05_confusion_matrix.png`

## Files
- RapidMiner process: `/process/titanic_decision_tree.rmp`
- Screenshots: `/screenshots/`
