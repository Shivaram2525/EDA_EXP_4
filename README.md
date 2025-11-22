# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis

```
Name : Shivaram M.
Register No. : 212223040195
```

## Aim

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.

## Algorithm

### 1)Import Libraries:

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

### 2)Load the Dataset:

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

### 3)Data Inspection:

View the first few rows using head().

Get dataset summary using info() and describe().

### 4)Handle Missing Data:
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

### 5)Univariate Analysis:
Perform univariate analysis for each variable:

### Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)
Use frequency tables and count plots.

### Numerical Variables: (e.g., Age, Fare)
Use histograms, box plots, and summary statistics.

### 6)Interpretation:
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


## Program

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset("Titanic")
print("The first 5 rows are :")
df.head()
df.shape
df.isnull().sum()
df.info()
df.describe()
print(df['sex'].value_counts())
survived_percentage=df['survived'].value_counts(normalize=True)*100
dead=round(survived_percentage[0],3)
alive=round(survived_percentage[1],3)
print(f"Alive : {alive}")
print(f"Dead : {dead}")
df['pclass'].value_counts()
df['embarked'].value_counts()
df['deck'].value_counts(sort=True)
sns.histplot(df['age'],bins=30,kde=True,color='black')
print(f"mean : {df['age'].mean()}")
print(f"Median : {df['age'].median()}")
print(f"Range : {max(df['age']-min(df['age']))}")
sns.boxplot(df['fare'])
plt.grid(True)
sns.histplot(df['fare'],bins=30,kde=True,color='black')
Mean=df['fare'].mean()
Median=df['fare'].median()
print(f"Mean : {Mean}")
print(f"Median : {Median}")
if Mean > Median:
    print("Its positively skewed.")
else:
    print("Its negatively skewed.")
```

## Output
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 57 46 AM" src="https://github.com/user-attachments/assets/bc4d0962-12b7-4bc8-a591-704dedae1d8b" />
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 57 52 AM" src="https://github.com/user-attachments/assets/fbe5f85f-8230-445e-a4a8-1a9c4ba4e7b1" />
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 57 56 AM" src="https://github.com/user-attachments/assets/f202057b-05b5-4738-b21c-36996772b1c0" />
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 58 02 AM" src="https://github.com/user-attachments/assets/22a6b866-100a-41be-a199-de49c3c40807" />
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 58 09 AM" src="https://github.com/user-attachments/assets/bb7665b6-81d6-4d24-a47f-d572dc7c1414" />
<img width="1680" height="1050" alt="Screenshot 2025-11-22 at 9 58 16 AM" src="https://github.com/user-attachments/assets/9193a6a6-4def-42a2-b14c-5a8da7a6eeb4" />



## Result
From the univariate analysis:

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.

### Visualization:
Plot appropriate charts for each variable using Matplotlib/Seaborn.
