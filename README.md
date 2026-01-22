🐍 Task 5: Python Basics – Reading Data & Simple Cleaning (Pandas)
📌 Project Overview

This task focuses on using Python with Pandas to perform basic data cleaning operations that are commonly done manually in Excel.
The objective is to learn how Python can automate data cleaning for large datasets efficiently.

📂 Dataset

One of the following datasets was used:

Titanic Dataset

House Prices Dataset

Students Performance Dataset

🛠 Tools & Libraries

Primary: Google Colab

Alternatives: Jupyter Notebook, Kaggle Notebooks

Libraries:

pandas

numpy

📁 Project Files
File	Description
Task5_Cleaning.ipynb	Jupyter notebook with all cleaning steps
cleaned_data.csv	Final cleaned dataset
README.md	Project documentation
🔹 Step 1: Import Libraries & Load Data
import pandas as pd
import numpy as np

df = pd.read_csv("titanic.csv")
df.head()


📌 Purpose: Load dataset and preview first few rows.

🔹 Step 2: Understand Data Structure
df.info()
df.shape


📌 Purpose: Check columns, data types, and total records.

🔹 Step 3: Identify Missing Values
df.isnull().sum()


📌 Purpose: Find which columns have missing data.

🔹 Step 4: Handle Missing Values
# Fill numeric columns with mean
df['Age'] = df['Age'].fillna(df['Age'].mean())

# Fill categorical columns with mode
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])


📌 Purpose: Prepare data for analysis or modeling.

🔹 Step 5: Remove Duplicates
before = df.shape[0]
df = df.drop_duplicates()
after = df.shape[0]

print("Rows before:", before)
print("Rows after:", after)


📌 Purpose: Ensure no duplicate records exist.

🔹 Step 6: Convert Data Types
df['Survived'] = df['Survived'].astype(int)


📌 Purpose: Make sure data types are correct for calculations.

🔹 Step 7: Create New Column

Example: Age Category

df['Age_Group'] = np.where(df['Age'] < 18, 'Child', 'Adult')


📌 Purpose: Feature engineering / transformation.

🔹 Step 8: Save Cleaned Dataset
df.to_csv("cleaned_data.csv", index=False)
