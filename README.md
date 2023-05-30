# Ex-04-Multivariate-Analysis

# Aim:
To perform Multivariate EDA on the given data set.

## DATE:

GITHUB LINK:https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis.git

COLAB LINK:https://colab.research.google.com/drive/1TI7KaZCPdsimGBdqMABKtZQ1fFmdS25n?usp=sharing

# Explaination:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# Algorithm:
STEP 1 Import the built libraries required to perform EDA and outlier removal.

STEP 2 Read the given csv file.

STEP 3 Convert the file into a dataframe and get information of the data.

STEP 4 Return the objects containing counts of unique values using (value_counts()).

STEP 5 Plot the counts in the form of Histogram or Bar Graph.

STEP 6 Use seaborn the bar graph comparison of data can be viewed.

STEP 7 Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8 Save the final data set into the file.

# Program:

```


import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from google.colab import files
uploaded = files.upload()
df = pd.read_csv("SuperStore.csv")
df

df.info()

df.describe()

df.isnull().sum()

df['Sales'] = df["Sales"].fillna(df['Sales'].mode()[0])
df.isnull().sum()

df.dtypes

sns.scatterplot(df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)
df.info()

states=df.loc[:,["Postal Code","Sales"]]
states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Postal Code")
plt.ylabel=("SALES")
plt.show()

states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Segment")
plt.ylabel=("Sales")
plt.show()

df.corr()

sns.heatmap(df.corr(),annot=True)

```

# Output:

Dataset

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/01.jpg)

Dataset information

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/02.jpg)

Data describe

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/03.jpg)

Checking and cleaning of null values

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/04.jpg)

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/05.jpg)

Data types

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/06.jpg)

Scatterplot

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/07.jpg)

Barplot

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/08.jpg)

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/09.jpg)

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/10.jpg)

Correlation coefficient interpretation

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/11.jpg)

Heatmap

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/12.jpg)

# Result:
Thus we have read the given data and performed the multivariate analysis with different types of plots.

