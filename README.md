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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/78d874d6-5702-475f-86a9-1c0e0cfc29db)

```
df.info()
```
![image](https://github.com/user-attachments/assets/eba741c8-2314-4886-8156-a7b098cb4e2a)
```
df.shape
```
![image](https://github.com/user-attachments/assets/6c880236-6188-41f7-a8f0-6e26d84b9a05)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/a739e3b1-41d5-43f7-bd38-1c4f8cb6384a)
```
df.shape
```
![image](https://github.com/user-attachments/assets/9652a367-957e-463a-994f-8f2e6f598d5a)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/04d7dd2c-0305-400b-9c0f-8b3f03f57c49)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/a052ebfc-b5b6-4815-a5ad-65334fa5bf1d)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/5c042536-d4dc-46bb-8d50-daf719ca3ca9)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/38f29114-5fc5-4359-a40b-33fb60772288)
```
df
```
![image](https://github.com/user-attachments/assets/409278f0-c159-4ee0-b846-b73d7f259076)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/710442c6-2d82-483e-b3e8-0931130e6060)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/96ec19df-39b4-4eb5-97f5-090ae0a53203)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/a316372a-d3a8-4b78-90c2-c51fa735d602)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/ee90f8fa-e2db-4d4b-ba4a-814c69d4f55b)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/36c28c5e-3000-49ed-8b43-da21ff974715)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/028a50f9-4420-4bcc-903b-700d5055d9f3)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/a3d68b52-5ce2-4281-a7b1-4a181435a573)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/0d9dfebc-1804-4833-b91d-2317d9f6c81f)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/529e0c72-14fe-4e73-ba08-5e978095fbcc)
```
numeric_df = df.select_dtypes(include=[np.number])
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/60e05d48-0ab2-4867-8c9f-07225f9e9233)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/ccdf548a-c64a-4c30-9758-b75beeb21308)


# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully.      
