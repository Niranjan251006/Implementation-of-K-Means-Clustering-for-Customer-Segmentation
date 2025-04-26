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
Developed by: Niranjan S
RegisterNumber:  212224040221
*/

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
plt.xlabel("No_of_Clusters"
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

1.DATA.HEAD()
![324681219-2aa57a0f-71f5-4bb8-977b-b3490b5905fd](https://github.com/user-attachments/assets/e8adf3e8-a479-4102-9843-8964528355fb)
2.DATA.INFO()
![324681362-f3c0d3fc-766c-4205-80cb-cb4a5c87a53f](https://github.com/user-attachments/assets/6d86ae0a-b993-4cc6-b6cd-fcdb1d538c01)
3.DATA.ISNULL().SUM()
![324681452-3c654b06-3ced-405c-b85f-ddc11cfc3617](https://github.com/user-attachments/assets/8abba01c-9067-4446-b981-0e0e0244033c)
4.PLOTTING WITH ELBOW METHOD
![324681523-927cc373-0f90-40b0-b637-17149b1f49b8](https://github.com/user-attachments/assets/3266d169-bd77-448b-954d-65b29986f8b8)
5.K MEANS CLUSTERING
![324681656-43712d0f-3206-46e7-a34f-d702ccf2f601](https://github.com/user-attachments/assets/4bf9614b-6d7e-4ad5-bf07-221cdd8a3292)
6.Y_PRED ARRAY
![324681712-8c1dfa0f-6869-41b3-833f-6195aaba55fe](https://github.com/user-attachments/assets/9c4ed7bf-81b2-4c00-8f46-97c0246a12d5)
7.CUSTOMER SEGMENT
![324681774-1dd609e5-c2f4-4d54-9bce-55def289240b](https://github.com/user-attachments/assets/1bc3ec12-2b5c-477f-a500-d06358777a96)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
