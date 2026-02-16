# Titanic Survival Prediction (Decision Tree) – RapidMiner

## Overview
This project builds a Decision Tree classifier in RapidMiner to predict Titanic survival (`Survived`) using data cleaning, feature engineering and model evaluation.

## Tools
- RapidMiner Studio
- Decision Tree (Gain Ratio)
- Train/Test split + Apply Model + Performance

## Dataset
Titanic dataset (provided in course materials).
> Note: Dataset is not included in this repo if restricted by course policy.

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
