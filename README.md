# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary python packages using import statements.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print all the outputs.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Karthikeyan.K
RegisterNumber: 212221230046
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")
data.info()
data.head()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
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
plt.title("Customer Segments")
```

## Output:
![image](https://user-images.githubusercontent.com/93427303/200994225-36da2de7-f244-4c56-91c3-8691a8342548.png)

![image](https://user-images.githubusercontent.com/93427303/200994305-6b00efaa-821d-4cf9-9a88-17d0fe22199e.png)

![image](https://user-images.githubusercontent.com/93427303/200994440-dbc49328-3314-4b99-a51e-1fad78ea4135.png)

![image](https://user-images.githubusercontent.com/93427303/200994523-6f104cb8-ab7b-4f9f-9e5c-f675279a0870.png)

![image](https://user-images.githubusercontent.com/93427303/200994798-3b76769f-b79f-471e-9046-312bc3eae3c0.png)

![image](https://user-images.githubusercontent.com/93427303/200994830-c9f6580e-36d1-43d6-9b7e-b62ad40885be.png)

![image](https://user-images.githubusercontent.com/93427303/200994860-551c98f3-8c2e-476a-add7-c111166e4a69.png)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
