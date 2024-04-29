# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
STEP1: Start

STEP2:Import the necessary packages using import statement.

STEP3:Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

STEP4:Import KMeans and use for loop to cluster the data.

STEP5:Predict the cluster and plot data graphs.

STEP6:Print the outputs and end the program

STEP7: Stop
## Program:

/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sanjay K
RegisterNumber:  212223220094
*/


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:/Users/admin/Downloads/Mall_Customers.csv")

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
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"],c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"],c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"],c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"],c="magenta", label="cluster4") 
plt.legend()
plt.title("Customer Segments")


## Output:
### head()
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/784fd469-267f-41c9-a574-bccfe43355f3)
### info()
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/01ac2987-8019-4519-bb38-6752ee3aaf4e)
### isnull() 
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/c2a860a9-d3d4-40c5-aeed-325843dfd0ee)
### Elbow Method
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/19ae713d-c1fd-4da3-8cfa-87188451296b)
### K Means
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/75d2d11f-0947-403b-8399-484cabf65ec4)
### Y_pred
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/65967f55-b222-4902-b6d3-ca54fda6b231)
### Customer Segments
![image](https://github.com/SanjayBalaji0/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145533553/d553703e-64bb-4cdb-ad53-4966c0c30fb6)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
