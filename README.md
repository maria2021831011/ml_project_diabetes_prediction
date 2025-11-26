# ml_project_diabetes_prediction


Diabetes Prediction Dataset – Exploratory Data Analysis (EDA)
Overview

This project contains an Exploratory Data Analysis (EDA) performed on the Diabetes Prediction Dataset. The main goal of this analysis is to understand the dataset, detect missing values, outliers, and feature relationships, and visualize the distribution of key variables.

1)  Libraries Used
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   import seaborn as sns

pandas: Load and manage the dataset

numpy: Numerical calculations

matplotlib & seaborn: Data visualization

2)  Load Dataset
   df = pd.read_csv('/content/diabetes_prediction_dataset.csv')

The dataset is loaded into a DataFrame for analysis.

   3.Basic Overview
df.describe()                #summary statistics of numeric columns
df.describe(include='all')   #summary statistics for all columns
df.isnull().sum()            # missing values per column
df.shape                     # number of rows and columns
df.columns                   #column names

Understanding data types, size, and missing values

Quick overview of categorical and numeric features

4. Feature Distributions (Histogram)
   df.hist(figsize=(20, 15), color='skyblue', edgecolor='black')
   plt.suptitle("Feature Distributions)", fontsize=18)
   plt.show()

Histograms show the distribution of numeric features

Helps identify skewed features or unusual patterns

5. Outlier Detection (Boxplot)
plt.figure(figsize=(20, 8))
df.boxplot()
plt.show()

Boxplots help detect outliers in numeric features

Points outside the box are potential outliers

6. Correlation Heatmap
sns.heatmap(df.select_dtypes(include=['number']).corr(), annot=True, cmap='coolwarm')
plt.show()

Displays pairwise correlation between numeric features

Strong positive correlation → 1

Strong negative correlation → -1

7. Scatter Plot Example
sns.scatterplot(data=df, x="blood_glucose_level", y="bmi", hue="diabetes")
plt.title("Blood Glucose Level vs BMI")
plt.show()

Visualizes relationship between blood_glucose_level and bmi

hue="diabetes" shows the difference between diabetic and non-diabetic classes

8. Pairplot (Feature Relationships)
sns.pairplot(df)
plt.show()

Pairplot shows scatter plots and histograms for all numeric features

Helps identify patterns, clusters, and feature interactions

⚠ For large datasets, consider using a sample (e.g., df.sample(1000)) to avoid performance issues

9. Missing Value Heatmap
plt.figure(figsize=(25, 8))
sns.heatmap(df.isnull(), cbar=False, cmap='viridis')
plt.title("Missing Value Map", fontsize=16)
plt.xticks(rotation=45)
plt.show()

Visualizes missing values across the dataset

Quickly identifies columns with missing data
