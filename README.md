# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages.
2. Analyse the data.
3. Use the elbow method by importing Kmeans.
4. Plot the graph according.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Lubindher S
RegisterNumber:  212222240056
*/
```
```
import pandas as pd 
import matplotlib.pyplot as plt 
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]


for i in range(1,11):
  kmeans = KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans (n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="magenta",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="orange",label="cluster4")
plt.legend()
plt.title("Customer segments")
```
## Output:
### data.head()
 ![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/9e5a9374-c999-4313-b1ae-d4464820a4f2)
### data.info()
![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/1c3025c1-b2c8-4307-9a34-257793c83b7f)
### data.isnull.sum()
![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/c0359d0d-0ad9-4d72-9489-a8249db0ed55)
### Elbow Method Graph()
![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/b4833cb2-7d58-46bd-88ac-c67cb05da05e)
### KMeans Cluster
![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/6a33447c-7b25-41eb-88a0-5af27721a631)
### Customer Segment Graph
![image](https://github.com/Archana2003-Jkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427594/037d42b0-b8cd-446b-9adb-4c3ec376c586)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
