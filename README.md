## Cerbral stroke Predicition

 Made by [Masa Aladwan](https://github.com/MasaAladwan) and [Asim](https://github.com/asiiiiiim)
 This repository contains the code and models used to predict the likelihood of a cerebral stroke based on various features such as age, BMI, heart disease history, work type, smoking status, and more. The project uses machine learning techniques to handle imbalanced datasets, address missing values, and implement multiple classification models for stroke prediction.


# Project Overview 
The goal of this project is to predict whether a patient is likely to experience a cerebral stroke based on multiple health-related features. Given the imbalanced nature of the data, various methods are applied to tackle the challenges, including resampling techniques and the use of advanced classification models.


## Dataset

The dataset contains several features such as:
	•	Age
	•	BMI (Body Mass Index)
	•	Gender
	•	Work Type
	•	Smoking Status
	•	Stroke (target variable)
	•	Heart Disease History
	•	Residence Type

 ## Key Observations 
  - The dataset is imbalanced with respect to stroke occurrence.
	- There are missing values in some columns, including BMI, which required different imputation strategies.

## Data Preprocessing
 1. Handling Missing Values:
	  •	BMI Missing Values: Two imputation strategies were applied:
	      •	 KNN Imputation
	      •	Iterative Imputation (Interpolation)
	  •	The dataset was divided into two versions based on the imputation method: one with KNN imputed values and another with interpolated values.

2. Outlier Detection:
    •	The dataset contains outliers, such as ages below 1 and extremely high BMI values. These were kept to preserve valuable information as they may represent rare but significant cases for model training.

3.	Categorical Encoding:
	  •	Label encoding was performed on categorical features to convert them into numeric form for model processing.

4.	Feature Binning:
  	•	The age and BMI features were binned into intervals to better capture the distribution of stroke occurrences across different groups.
	  •	Age bins: [0 - 18, 19 - 30, 31 - 45, 46 - 60, 61 - 75 , 76 - 90 , 91 - 100 ]
  	•	BMI bins: ['Underweight', 'Normal weight', 'Overweight', 'Obese I', 'Obese II', 'Obese III']
5.	Handling Class Imbalance:
  	•	Oversampling was applied to the stroke (1) class using RandomOverSampler.
   	•	Undersampling was applied to the non-stroke (0) class using RandomUnderSampler.
  	•	The model performance with oversampling was observed to be suboptimal due to excessive stroke samples.

## Visualization

Various visualizations were generated to explore the data, such as:
	•	Distribution of strokes by gender, work type, and age.
	•	Relationship between features like BMI and stroke.
	•	Stroke distribution across different intervals for age and BMI.

## Machine Learning Models

The following classifiers were evaluated on both versions of the dataset (KNN imputed and interpolated):
	•	AdaBoost
	•	Gradient Boosting
	•	XGBoost (XGB)
	•	CatBoost
	•	Bagging
	•	Random Forest
	•	LightGBM (LGBMClassifier)
	•	Stacking Classifier

##Evaluation Metrics 

For each model, the following evaluation metrics were recorded:
	•	Accuracy
	•	Precision
	•	Recall
	•	F1-score
	•	Support (for each class)
The classification report was generated for each model to evaluate its performance.

## Model Selection

The Stacking Classifier, which combines the predictions from different models, was also tested to see if ensemble learning improved the results. Each classifier’s performance was thoroughly evaluated to determine the best method for stroke prediction.

## Conclusion

This project demonstrates a complete pipeline for predicting cerebral stroke risk using machine learning. Various imputation techniques, handling of imbalanced data, and multiple classification models were employed to achieve optimal results. The insights gained from data visualizations an

## Requirements:
Install dependencies:

```bash
pip install -r requirements.txt
```
