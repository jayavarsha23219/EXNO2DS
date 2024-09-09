# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
# DEVELOPED  BY : JAYAVARSHA T
# REG NO : 212223040075

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/79e62e20-c5f5-45ab-83a5-cd3dea1002d5)
```
df.head(10)
```
![image](https://github.com/user-attachments/assets/6c705b88-c4ae-4bdd-b1fa-a5be00840e33)
```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/ac5bd273-8c92-4092-b2ea-7bd37003d12d)
```
df.info()
```
![image](https://github.com/user-attachments/assets/e79f64e1-da5d-48d5-b58d-e6e574de90c0)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/244b56e5-2f4e-4dbc-8dac-382233617997)
```
df.shape
```
![image](https://github.com/user-attachments/assets/84d9527d-7436-4de2-bd5f-34464890b751)
```
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/b6e4a899-b360-4dc9-980c-78b3969b0fd2)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/4e82e657-d2ca-4b76-9124-7d1bb4343568)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/5b3c2e34-dc89-4ccf-b141-abe09759793a)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/a4b59368-0d92-4d80-9bfb-b002db960f59)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/600e15ae-9a94-4e40-8b20-ab79d2cc53c8)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/d03343e0-def2-4767-a761-ee755476090a)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
![image](https://github.com/user-attachments/assets/7e793254-3312-434d-a063-bfe564c5538b)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/68677808-9e03-43a5-88db-2f4751d93f28)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/114345a1-ea76-4dff-9a46-6c4bf57ae63c)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/a4e10f2b-3f89-4370-8ff3-a9ad699912a4)
```
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
![image](https://github.com/user-attachments/assets/8332033f-a02b-4309-9c38-44958dff0249)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/657d0548-eca6-443c-8bb4-3a6daeeb7e42)
```
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/fb1e76c5-7e2d-4087-81e8-044901f108db)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/f6acc866-4d38-4b1f-ba55-999f90277498)
![image](https://github.com/user-attachments/assets/6deaa5bc-9e9d-4753-b173-a5859bb9951e)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
