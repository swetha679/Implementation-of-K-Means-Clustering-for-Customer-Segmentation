# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipment Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data into the model
4. Plot the Cluster graph

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: B R SWETHA NIVASINI
Register Number:  212224040345

```

```
import pandas as pd
 import matplotlib.pyplot as plt
 data = pd.read_csv("C:/Users/LENOVO/Downloads/Mall_Customers.csv")
 data.head()
 data.info()
 data.isnull().sum()
 from sklearn.cluster import KMeans
 wcss = [] 
 for i in range(1,11):
 kmeans = KMeans(n_clusters = i,init = "k-means++")
 kmeans.fit(data.iloc[:,3:])
 wcss.append(kmeans.inertia_)
 plt.plot(range(1,11),wcss)
 plt.xlabel("No. of Clusters")
 plt.ylabel("wcss")
 plt.title("Elbow Method")
 km = KMeans(n_clusters = 5)
 km.fit(data.iloc[:,3:])
 y_pred = km.predict(data.iloc[:,3:])
 y_pred
 data["cluster"] = y_pred
 df0 = data[data["cluster"]==0]
 df1 = data[data["cluster"]==1]
 df2 = data[data["cluster"]==2]
 df3 = data[data["cluster"]==3]
 df4 = data[data["cluster"]==4]
 plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluste
 plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="clu
 plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="clust
 plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="clu
 plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="c
 plt.legend()
 plt.title("Customer Segments")
```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)

![Screenshot 2025-04-19 170620](https://github.com/user-attachments/assets/25835f21-a73f-4da3-99e7-1802d6db3024)


![Screenshot 2025-04-19 170628](https://github.com/user-attachments/assets/89842ef4-0e1c-462f-9436-5a1164260777)


![Screenshot 2025-04-19 170637](https://github.com/user-attachments/assets/597e7391-7507-460d-9bc2-8c527086a91d)

![Screenshot 2025-04-19 170731](https://github.com/user-attachments/assets/eb4ae127-392f-4426-b9f4-3868078fbc5c)

![Screenshot 2025-04-19 170759](https://github.com/user-attachments/assets/2128ed5d-b37c-49ed-b14a-b527e789dad6)


![Screenshot 2025-04-19 170808](https://github.com/user-attachments/assets/5e700e97-fe67-469e-8c3c-b034a6c61480)









## Result:
Thus, the program to implement the K Means Clustering for Customer Segmentation is written and verified using Python programming.
