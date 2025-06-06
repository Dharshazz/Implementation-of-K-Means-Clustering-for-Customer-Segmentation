# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: THARSHAN R
RegisterNumber:  212223223004
*/
```
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```


## Output:

1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/6e391371-6d33-42b8-a74f-42caa8fd5a61)

2.DATA.INF0():
![image](https://github.com/user-attachments/assets/defbb2a1-5b5a-4a01-ba83-0a075282c56d)

3.DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/d9f4429e-3a0e-427b-9ebe-1ad5643a9adc)

4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/71964759-0d95-4c68-9cb9-d49c9acf4a0f)

5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/f437066a-2d99-44d7-9663-b01b0109fbe3)

6.Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/33b3bce0-1b57-4ba1-a52e-dc2ea69e0241)

7.CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/48c0dc78-26cf-4de2-8f0e-fa86b3150916)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
