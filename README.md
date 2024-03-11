# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
## STEP 1:
Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

## STEP 2:
Replace the null value using any one of the method from mode,median and mean based on the dataset available.

## STEP 3:
Use boxplot method to analyze the outliers of the given dataset.

## STEP 4:
Remove the outliers using Inter Quantile Range method.

## STEP 5:
Use Countplot method to analyze in a graphical method for categorical data.

## STEP 6: 
Use displot method to represent the univariate distribution of data.

## STEP 7: 
Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

## STEP 8: 
Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![alt text](o1.png)
```python
df.head()
```
![alt text](o2.png)
```python
df.tail()
```
![alt text](o3.png)
```python
df.describe()
```
![alt text](o4.png)
```python
df.info()
```
![alt text](o5.png)
```python
df.shape
```
![alt text](o6.png)
```python
df.set_index("PassengerId",inplace=True)
df
```
![alt text](o7.png)
```python
df.nunique()
```
![alt text](o8.png)
```python
df["Survived"].value_counts()
```
![alt text](o9.png)
```python
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![alt text](o10.png)
```python
sns.countplot(data=df,x="Survived")
```
![alt text](o11.png)
```python
df.Pclass.unique()
```
![alt text](o12.png)
```python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![alt text](o13.png)
```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![alt text](o14.png)
```python
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
![alt text](o15.png)
```python
df.boxplot(column="Age",by="Survived")
```
![alt text](o16.png)
```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![alt text](o17.png)
```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![alt text](o18.png)
```py
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![alt text](o19.png)
```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![alt text](o20.png)
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![alt text](o21.png)
```py
sns.pairplot(df)
```
![alt text](o22.png)
# RESULT
The EDA Analysis using python is executed successfully.
