# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis

**Aim**

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.


**Algorithm**

**1)Import Libraries:**

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

**2)Load the Dataset:**

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

**3)Data Inspection:**

View the first few rows using head().

Get dataset summary using info() and describe().

**4)Handle Missing Data:**
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

**5)Univariate Analysis:**
Perform univariate analysis for each variable:

**Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)**
Use frequency tables and count plots.

**Numerical Variables: (e.g., Age, Fare)**
Use histograms, box plots, and summary statistics.

**6)Interpretation:**
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


**Program**

**Name :NARESH.R

Reg No.:212223240104

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = sns.load_dataset('titanic')

print("First 5 Records:")
display(df.head())
df.shape
df.isnull().sum()
df.columns
sns.countplot(x='sex', data=df)
plt.title("Distribution of Gender")
plt.pie(df['survived'].value_counts(),labels=['Survived', 'Not Survived'], 
        autopct='%1.1f%%', startangle=90)
plt.title('Survival Distribution')
plt.axis('equal')
plt.show()
df['survived'].value_counts()
df['survived'].mean()*100
df['pclass'].value_counts()
df['pclass'].value_counts().max()
df['deck'].value_counts().max()
df['embarked'].value_counts()
df['age'].mean()
sns.histplot(df['age'].dropna(), kde=True)
plt.title("Distribution of Passenger Age")
plt.xlabel("Age")
plt.ylabel("Count")
plt.show()
df['age'].skew()
sns.boxplot(x=df['fare'])
plt.title("Boxplot of Fare")
plt.show()
sns.histplot(df['fare'].dropna(), kde=True)
plt.title("Distribution of Passenger Age")
plt.xlabel("Age")
plt.ylabel("Count")
plt.show()
df['fare'].median()
df['pclass'].value_counts()
df['fare'].mean()

**Output**


**Result**
From the univariate analysis:

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.

Visualization:
Plot appropriate charts for each variable using Matplotlib/Seaborn.
