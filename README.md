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
## DataSet:
![multi1](https://user-images.githubusercontent.com/118671457/230135275-8379ff55-2003-4d78-ab2d-4d49e8bcb1c1.png)
## Head:
![mul2](https://user-images.githubusercontent.com/118671457/230135416-24e57a83-5cc1-49fb-8406-443fc5896243.png)
## Info:
![mul3](https://user-images.githubusercontent.com/118671457/230136666-a71cf6eb-67e4-46da-bc6c-33aa171e1d4a.png)

## Describe & Isnull:
![mul4](https://user-images.githubusercontent.com/118671457/230135708-cfc5b734-53b8-43a8-af8c-b122c9996925.png)
## Data Type::
![mul5](https://user-images.githubusercontent.com/118671457/230135820-9814ea36-d4e7-4b1b-9bc5-eeaa5c6d4166.png)
## ScatterPlot:
![mul6](https://user-images.githubusercontent.com/118671457/230135871-abbcedf1-a17e-41cb-bba5-277feb5b5bb1.png)
## Bar Plot:
![mul7](https://user-images.githubusercontent.com/118671457/230135913-40feffd2-b2d5-4ea5-96d7-6688946a7527.png)
![mul8](https://user-images.githubusercontent.com/118671457/230136199-264ce8a4-37da-4509-b22a-3ccf12e286e0.png)
## SEGMENTATION:
![mul9](https://user-images.githubusercontent.com/118671457/230136269-cfd70653-f319-4f16-875a-4709ec154de9.png)
## SUBPLOTS & CORRESSION:
![mul10](https://user-images.githubusercontent.com/118671457/230136308-376dfa74-ebbb-4ea9-b373-a0a847273ad5.png)
## Heat Map:
![mul11](https://user-images.githubusercontent.com/118671457/230138580-13eb4d25-c2d1-4432-aa06-4ada197b74fc.png)

![mul12](https://user-images.githubusercontent.com/118671457/230136378-0d401f46-8499-495a-aa87-f2de202e70a7.png)



