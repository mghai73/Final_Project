# **Absence Prediction Model**

This project is a part of the AAI-500 course in the Applied Artificial Intelligence Program at the University of San Diego (USD).
Project Status: Completed

## **Team Members:**
1. MUNISH GHAI
2. ANTAREEP CHAKRABORTY
3. ANAND BAJPAI

## **Installation:**

To use this project, first clone the repo on your device using the command below:
git init
git clone https://github.com/mghai73/Final_Project

## **Project Objective:**
Building a project for Absenteeism at Work Prediction can be an insightful analysis, especially for organizations aiming to reduce absenteeism by identifying patterns and addressing underlying causes. It may be due to health issues, personal/family issues, workplace environment, lack of motivation, burnout, age related etc. 
The Hybrid, Remote, On-site discussions are some of the biggest challenges organizations are facing today post the pandemic. Whereas sporadic absenteeism is natural, excessive absenteeism can severely affect an organization's productivity, team morale, and overall business performance. Identifying the causes of absenteeism and addressing them in advance is important to surmount this problem.

## **Description:**
This Python script demonstrates how to use a pre-trained machine learning model to predict employee absenteeism based on various features. The script preprocesses new input data using a scaler, then uses a model to predict whether an employee will be absent (1) or not absent (0).


## **Acquiring the Dataset:**
The dataset can be downloaded as per below details:
•	Website: (https://archive.ics.uci.edu/dataset/445/absenteeism+at+work)
•	Dataset Background: The database was created with records of absenteeism at work from July 2007 to July 2010 at a courier company in Brazil.
•	It has Reason for absence (21 ICD variables and 7 categories without CID) and 21 variables (features) which includes ID (which is dropped) and 21st being Absenteeism time in hours being the target.

## **Features:**
•	Feature List: The model uses 19 features related to employee absenteeism, such as transportation expense, distance from residence to work, service time, social habits, and more.
•	Model Input: The input data should be provided as a list, with values matching the feature order used during training.
•	Prediction Output: The model predicts absenteeism as either 1 (Absent) or 0 (Not Absent).

## **Prerequisites:**
To run this script, you need to install the following Python libraries:
•	pandas
•	scikit-learn
You can install them using pip:
bash
Copy
pip install pandas scikit-learn




## **Code Overview:**

### **1. Data Preparation**
The script starts by defining a list of new data. This data should match the features used during model training. The features include:
•	Reason for absence
•	Month of absence
•	Day of the week
•	Seasons
•	Transportation expense
•	Distance from residence to work
•	Service time
•	Age
•	Work load average/day
•	Hit target
•	Disciplinary failure
•	Education
•	Son
•	Social drinker
•	Social smoker
•	Pet
•	Weight
•	Height
•	Body mass index


### **2. Data Pre-processing**
The input data is transformed into a pandas DataFrame with the appropriate column names. The data is then scaled using a pre-trained scaler.



### **3. Model Prediction**
After scaling the input data, the script uses a pre-trained model to predict whether the employee will be absent or not.

### **4. Output**
The script outputs the prediction result as either 1 (Absent) or 0 (Not Absent).

Full Script
python
Copy
import pandas as pd


# Example new data
new_data = [[26, 7, 4, 1, 179, 51, 13, 33, 239.554, 0, 0, 1, 2, 1, 0, 1, 89, 172, 31]]

# List of feature names used for training (ensure this matches the training data columns)
feature_names = [
    'Reason for absence', 'Month of absence', 'Day of the week', 'Seasons',
    'Transportation expense', 'Distance from Residence to Work',
    'Service time', 'Age', 'Work load Average/day ', 'Hit target',
    'Disciplinary failure', 'Education', 'Son', 'Social drinker',
    'Social smoker', 'Pet', 'Weight', 'Height', 'Body mass index'
]

# Create a pandas DataFrame with the new data and correct column names
new_data_df = pd.DataFrame(new_data, columns=feature_names)

# Scale the new data using the scaler (which was fitted on the training data)
new_data_scaled = scaler.transform(new_data_df)  # Using the DataFrame

# Make the prediction
prediction = model.predict(new_data_scaled)

# Print the prediction result
print("Prediction (1: Absent, 0: Not Absent):", prediction[0])


### **Notes**
•	The model and scaler should already be pre-trained and saved before running this script. You can use any classification model (e.g., Random Forest, Logistic Regression, etc.) for training.
•	Ensure that the feature names in the feature_names list exactly match those used during model training.
•	This script assumes the scaler and model are already loaded in the environment.

