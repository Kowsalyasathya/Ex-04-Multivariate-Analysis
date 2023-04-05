# Ex-04-Multivariate-Analysis
## ALGORITHM:
## STEP 1

Import the built libraries required to perform EDA and outlier removal.
## STEP 2

Read the given csv file.
## STEP 3

Convert the file into a dataframe and get information of the data.
## STEP 4

Return the objects containing counts of unique values using (value_counts()).
## STEP 5

Plot the counts in the form of Histogram or Bar Graph.
## STEP 6

Use seaborn the bar graph comparison of data can be viewed.
## STEP 7

Find the pairwise correlation of all columns in the dataframe.corr() .
## STEP 8

Save the final data set into the file.
## PROGRAM:
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.isnull().sum()

data.dtypes

sns.scatterplot(x=data['Postal Code'],y=data['Region'])

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]] 
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SEGMENT") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(x=data['Ship Mode'],y=data['Sales'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=False)

plt.figure(figsize=(10,7))
sns.scatterplot(x=data['Sub-Category'],y=data['Sales'], hue=data['Ship Mode'])
plt.xticks(rotation = 90)

## Output:

