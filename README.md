# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis
#### Name :SUDARSHANA S

#### Reg No.:212223050054

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

#### Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)
Use frequency tables and count plots.

#### Numerical Variables: (e.g., Age, Fare)
Use histograms, box plots, and summary statistics.

### 6)Interpretation:
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


### Program

##### Data Understanding
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = sns.load_dataset("titanic")
df.head()

df.shape

df.isnull().sum()
```
##### Categorical Variable Analysis
```python
df["sex"].value_counts()

sns.countplot(x='sex', data=df)
plt.title("Distribution of Gender")
plt.show()
```
```python
print("percentage of passengers survived")
df["survived"].value_counts(normalize=True) * 100
```
```python
df["pclass"].value_counts()

sns.countplot(x='pclass', data=df)
plt.title("Passenger class distribution")
plt.show()
```
```python
df['embarked'].value_counts()

sns.countplot(x='embarked', data=df)
plt.title("passengers embarked from each port")
plt.show()
```
```python
df["deck"].value_counts()

sns.countplot(x='deck', data=df)
plt.title("Deck distribution")
plt.show()
```
##### Numerical Variable Analysis

```python
print("Mean distribution of age :",df["age"].mean())
print("Median distribution of age :",df["age"].median())
print("Range :",max(df["age"])-min(df["age"]))

plt.figure(figsize=(10, 6))
sns.histplot(df['age'].dropna(), bins=30, kde=True)
plt.title('Distribution of Passenger Age')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.grid(axis='y', alpha=0.75)
plt.show()
```
```python
plt.figure(figsize=(8, 6))
sns.boxplot(y='fare', data=df)
plt.title('Distribution of Passenger Fare')
plt.ylabel('Fare')
plt.grid(axis='y', alpha=0.75)
plt.show()
```
```python
print(f"Mean Fare: {df['fare'].mean():.2f}")
print(f"Median Fare: {df['fare'].median():.2f}")

plt.figure(figsize=(10, 6))
sns.histplot(df['fare'], bins=50, kde=True)
plt.title('Distribution of Passenger Fare')
plt.xlabel('Fare')
plt.ylabel('Frequency')
plt.grid(axis='y', alpha=0.75)
plt.show()
```

## Output

###  Data Understanding

<img width="1107" height="215" alt="image" src="https://github.com/user-attachments/assets/7568d697-06c9-4e4b-b148-7c5f3147e6d0" />

<img width="393" height="24" alt="image" src="https://github.com/user-attachments/assets/23862f5f-87a2-4b15-b2c3-c06af1c6f076" /><br><br>

<img width="385" height="629" alt="image" src="https://github.com/user-attachments/assets/350177d4-080e-4e55-8104-385af02f0aed" /><br><br>

### distribution of the sex variable

<img width="539" height="181" alt="image" src="https://github.com/user-attachments/assets/94fd9979-cf9a-429a-8966-ec12f2c34007" /><br><br> 

<img width="767" height="503" alt="image" src="https://github.com/user-attachments/assets/976bfd04-aec3-4ac6-a8d7-58fe57886d2d" /><br><br>

### percentage of passengers survived

<img width="576" height="206" alt="image" src="https://github.com/user-attachments/assets/6de3f352-127e-4e73-96a5-4f72273096eb" /><br><br>

### Passenger class distribution

<img width="665" height="224" alt="image" src="https://github.com/user-attachments/assets/405ed161-4595-46a0-9b3f-ecb7d3d53c65" />

<img width="683" height="510" alt="image" src="https://github.com/user-attachments/assets/61e6562e-a3e3-45b9-a03d-4be0eb7dd908" />

### passengers embarked from each port

<img width="690" height="217" alt="image" src="https://github.com/user-attachments/assets/c18152fe-98dd-4c59-9234-4bbafb70a2d9" />

<img width="732" height="506" alt="image" src="https://github.com/user-attachments/assets/c1e5b228-51c9-4b1a-b599-8b81f90784d0" />

### Deck distribution

<img width="539" height="356" alt="image" src="https://github.com/user-attachments/assets/fa0d556d-e287-48a0-b5bc-e31a7338f5b7" />

<img width="677" height="515" alt="image" src="https://github.com/user-attachments/assets/20230238-9ded-4861-a3d0-8ffa03571d6e" />

### mean, median, and range and distribution of passenger age

<img width="675" height="64" alt="image" src="https://github.com/user-attachments/assets/3a831954-89da-46ea-a238-f4f90f4b4da8" />

<img width="1000" height="616" alt="image" src="https://github.com/user-attachments/assets/2cbf22fd-e8fd-4cd1-a406-f5440c6b14de" />

### boxplot for fare

<img width="898" height="574" alt="image" src="https://github.com/user-attachments/assets/2cab99e9-692d-408e-a00f-201dcdf74758" />

### fare distribution

<img width="1056" height="655" alt="image" src="https://github.com/user-attachments/assets/c584f6ee-7414-491b-b8ca-7f6c0eca9cf0" />


## Result

From the univariate analysis: 

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.

Visualization:
Plot appropriate charts for each variable using Matplotlib/Seaborn.
