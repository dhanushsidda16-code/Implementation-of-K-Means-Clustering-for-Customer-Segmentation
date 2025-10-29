# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
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
Developed by: S Dhanush
RegisterNumber:  25005353
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
![K Means Clustering for Customer Segmentation](sam.png) 
##  1.DATA.HEAD():
<img width="892" height="312" alt="Screenshot 2025-10-29 112841" src="https://github.com/user-attachments/assets/b7855e42-7561-4020-ad7c-4e3b6af67ab6" />

##  2.DATA.INFO():
<img width="620" height="322" alt="Screenshot 2025-10-29 112851" src="https://github.com/user-attachments/assets/0c5dadbb-ba27-412e-9d66-ca0a8445b571" />

##  3.DATA.ISNULL().SUM():
<img width="321" height="345" alt="Screenshot 2025-10-29 112903" src="https://github.com/user-attachments/assets/2b162db2-c732-4468-aacc-74692f37d9ec" />

##  4.PLOT USING ELBOW METHOD:
<img width="948" height="584" alt="Screenshot 2025-10-29 112952" src="https://github.com/user-attachments/assets/e5392537-492e-4cdc-b9b0-c29bbaca6be2" />

##  5.K-MEANS CLUSTERING:
<img width="546" height="207" alt="Screenshot 2025-10-29 112913" src="https://github.com/user-attachments/assets/1bd180e5-9c82-4205-9e2b-ce09c00be1f6" />

##  6.Y-PRED ARRAY:
<img width="801" height="226" alt="Screenshot 2025-10-29 112931" src="https://github.com/user-attachments/assets/15ef8205-4bd5-4d70-a6a5-880dd84fd313" />

## 7.CUSTOMER SEGMENT:
<img width="785" height="577" alt="Screenshot 2025-10-29 112943" src="https://github.com/user-attachments/assets/f006b77b-e7c2-46ff-aa10-d0e80e1d3595" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
