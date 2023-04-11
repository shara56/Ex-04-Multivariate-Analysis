# Ex-04-Multivariate-Analysis
# Aim
To perform Multivariate EDA on the given data set.

# Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# Algorithm

# Step1
Import the built libraries required to perform EDA and outlier removal.

# Step2
Read the given csv file.

# Step3
Convert the file into a dataframe and get information of the data.

# Step4
Return the objects containing counts of unique values using (value_counts()).

# Step5
Plot the counts in the form of Histogram or Bar Graph.

# Step6
Use seaborn the bar graph comparison of data can be viewed.

# Step7
Find the pairwise correlation of all columns in the dataframe.corr()

# Step8
Save the final data set into the file.

# Code

Developed by : SHARANGINI T K

Registration Number : 212222230143
```
import pandas as pd
import numpy as py
import seaborn as sns
import matplotlib.pyplot as plt

df=pd.read_csv('SuperStore.csv')
df
df.head()
df.info()
df.describe()
df.isnull().sum()
df.dtypes

sns.scatterplot(df['Postal Code'],df['Sales'],hue=df['Row ID'])

sns.barplot(x=df['Row ID'],y=df['Sales'],data=df)

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

sns.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])

df.corr()
sns.heatmap(df.corr(),annot=True)
```
# Output

# Data
![image](https://user-images.githubusercontent.com/113497104/231059119-7d332d27-4e30-47d6-908a-374e711f9b1d.png)


# Data head
![image](https://user-images.githubusercontent.com/113497104/231059224-d5c8c037-b0c9-4595-9fe5-8e24995563de.png)


# Data Information
![image](https://user-images.githubusercontent.com/113497104/231059263-2858705d-e5de-4fea-8da1-c9361c3a9358.png)

# Data describe
![image](https://user-images.githubusercontent.com/113497104/231059301-208c7901-e6b4-411f-bb81-029d7771ed89.png)


# Data Null Values
![image](https://user-images.githubusercontent.com/113497104/231059369-98a468ba-1098-46ec-9b02-36399bfa7489.png)


# Data Types
![image](https://user-images.githubusercontent.com/113497104/231059397-8c8518b5-0ad9-40b5-95a9-90d72eaaf5d5.png)


# Scatterplot
![image](https://user-images.githubusercontent.com/113497104/231059448-5323c960-39bf-4abc-8a38-3411e5cc76e1.png)


# Barplot
![image](https://user-images.githubusercontent.com/113497104/231059482-bbb3cbf4-f614-41dd-bf3c-8d6c0f6070b8.png)
![image](https://user-images.githubusercontent.com/113497104/231059502-c3644620-bbb1-455c-b817-ed98ea3c06f6.png)
![image](https://user-images.githubusercontent.com/113497104/231059519-5c803492-232e-4a30-85b7-e8afa22d185d.png)

# Correlation and Heatmap
![image](https://user-images.githubusercontent.com/113497104/231059583-e9276352-7dc2-48e3-a166-825d4dee3fd9.png)

![image](https://user-images.githubusercontent.com/113497104/231059599-4b914af7-c10c-4e68-a369-f381a4af5696.png)


# Result
Thus the program to perform EDA on the given data set is successfully executed.
