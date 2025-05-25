![](UTA-DataScience-Logo.png)

## **Student Academic Performance**

* This repository holds an attempt to apply machine learning techniques to predict student academic performance based on demographic, academic, and extracurricular factors."Students Performance Dataset" Kaggle Challenge https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset

## Overview

* *This project looks at how I can use supervised machine learning to figure out if a student will pass or fail, based on things like gender, parental education, extracurricular activities, tutoring, and other factors. The dataset had both categorical and numerical features, so I had to preprocess it by using one-hot encoding for the categories and Min-Max scaling for the numbers. I trained and tested a few different classification models and looked at how well they did using accuracy, precision, recall, F1-score, and ROC-AUC.*


![Screenshot 2025-05-02 004803](https://github.com/user-attachments/assets/b9da57d7-bb8b-450a-81ee-df4d72efcba5)



![Screenshot 2025-05-02 004932](https://github.com/user-attachments/assets/8671db48-43fc-4b7c-9748-ca4f70dbd9a2)


## Summary of Workdone

### Data Summary

* Data Type: Tabular
  * Train.csv
    * 1,913 rows x 15 columns
  * Test.csv
    * 479 rows x 15 columns
    * Removed the target column (GradeClass)
  * The target column GradeClass serves as the indicator of student academic performance, which is later converted into a binary classification label (Pass_Fail) to distinguish between students who passed and those who failed.

![Screenshot 2025-05-02 020106](https://github.com/user-attachments/assets/c78fe51d-8d39-40f3-9bf4-976d23549059)

![Screenshot 2025-05-02 020235](https://github.com/user-attachments/assets/84e8f449-efbf-4b5d-b091-6cbcd1fb43bb)



  * The dataset contains a total of 2,392 student records. 1,913 instances were used for training, 479 for testing, and no separate validation set was used.

#### Preprocessing/ Clean up

* Duplicates: None
* Outliers: None
* Dropped Unnecessary Columns:
  * ("StudentID" , "GradeClass")
  They were dropped after creating the binary target, so they were excluded from training.


* One-Hot Encoding of Categorical Variables
  * ("Gender") (which represents as "Male" or "Female") was converted into numerical format using One-Hot Encoding. This created a separate binary column for each category. 

* Feature Engineering
  * A key feature engineering step was converting the ("GradeClass") into a binary target variable Pass_Fail
 
* Min-Max Scaling of Numerical Features
  * Numerical features were scaled to a 0–1 range using Min-Max scaling to improve model performance.
    
* Missing Values: None

  * **This dataset had a few issues, especially with the categorical features. Things like gender, ethnicity, parental education, and extracurriculars were all in text format, so I had to convert them using one-hot encoding before training any models. If I didn’t do that, the machine learning algorithms wouldn’t understand how to work with the data.
Also, there was a column like StudentID, which seemed important at first but didn’t actually help with the predictions. It’s just an identifier, so trying to calculate something like GPA from it wouldn’t make sense and would’ve taken a lot of time since it doesn’t really relate to how well a student performs.**

### Training

* Train: (80%) of train.csv
* Test: (20%) of test.csv
  * This output is based on predictions
 
![Screenshot 2025-05-02 042414](https://github.com/user-attachments/assets/68e8ea51-f3ab-4503-808f-cf3ae27b664b)

* Problem Formation
  * Training was the hardest process because after several attempts to make an ROC Curve those results, it couldn't function ROC Curve due to switching to binary classification and wouldn't align with results. For example:

    
![Screenshot 2025-05-02 084358](https://github.com/user-attachments/assets/4767a32b-5b99-49e5-9701-9ab246726a59)



![Screenshot 2025-05-02 111932](https://github.com/user-attachments/assets/a6aeca15-4667-4a29-9101-cce3f8c997aa)


### Conclusions

* This project showed me how machine learning can be used to predict whether a student will pass or fail, using different academic and personal details like gender, parental education, extracurriculars, and more. I had to do a lot of data cleaning first—like converting categorical data with one-hot encoding, scaling the numerical features, and dropping columns that weren’t helpful. After that, I trained and compared different models like Decision Tree, Random Forest, and XGBoost. I evaluated each one using metrics like accuracy, precision, recall, F1-score, and ROC-AUC to see how well they actually performed.
  
### Future Work

* I’d try would be improving the feature engineering—maybe combining some of the features or creating new ones that better represent a student’s academic behavior, like calculating a GPA or time spent studying per week. I’d also look into hyperparameter tuning more deeply, especially for models like XGBoost and Random Forest

## How to reproduce results
* 1. Clone Repository

* 2. Download the "📚 Students Performance Dataset 📚 https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset

  
* 3. Load the Dataset
  
     
* Preprocess the Data
  * Remove unnecessary columns like StudentID
  *  Encode categorical features using one-hot encoding
  * Fill in missing values
  * Scale numerical features using MinMaxScaler
  
* 4. Create Target Variable
  *  ["Pass_Fail"] = df["GradeClass"]apply
 
* 5. Split the Data
     * X_train, X_test, y_train, y_test = train_test_split

* 6. Train the Models

### Overview of files in repository

* Train ML Algorithm.ipynb
* Data Visualization.ipynb
* Data Cleaning and Pre-Processing.ipynb
* Data Loading and Initial Look.ipynb


### Software Setup
* Pandas as pd
* Sklearn.Preprocessing
* Train_test_split
* StandardScaler, OneHotEncoder
* Matplotlib.pyplot
* Sklearn.ensemble 
* Sklearn.tree


## Citations
@misc{rabie_el_kharoua_2024,
	title={📚 Students Performance Dataset 📚},
	url={https://www.kaggle.com/ds/5195702},
	DOI={10.34740/KAGGLE/DS/5195702},
	publisher={Kaggle},
	author={Rabie El Kharoua},
	year={2024}
}







