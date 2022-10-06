# Ex-04-Multivariate-Analysis
## AIM:
To perform Multivariate EDA on the given data set.
## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
## ALGORITHM:
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP 8
Save the final data set into the file.
## PROGRAM
```import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.isnull().sum()

data.dtypes

sns.scatterplot(data['Postal Code'],data['Sales'])

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES")
plt.ylabel=("SALES") 
plt.show()

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

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
## OUTPUT
### HEAD()
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/1.png)

### INFO()
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/2.png)

### DESCRIBE()
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/3.png)

### DATATYPE() 
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/4.png)

### ISNULL()
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/5.png)

### SCATTER PLOT
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/6.png)

### BARPLOT
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/7.png)

### SEGMENTATION
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/8.png)

### SUBPLOTS
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/9.png)

### CORRESSION
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/10.png)

### HEATMAP()
![O](https://github.com/dharanielango/Ex-04-Multivariate-Analysis/blob/main/11.png)

## RESULT
Hence The Performance of the Multivariate EDA on the given data set is verified.
