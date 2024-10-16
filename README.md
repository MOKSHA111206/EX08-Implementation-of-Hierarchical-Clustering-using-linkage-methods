# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.compute the distance between every pair of data points,resulting in a distance matrix

2.assign each data point to its own individual cluster

3.using a linkage criterion,find the two closest cluster and merge them

4.visualize the hierarchical clustering as a dendrogram

## Program:
```
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by:AMMINENI MOKSHASREE
RegisterNumber:2305001001

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:
![image](https://github.com/user-attachments/assets/ab426ba0-60da-44e9-888f-52a8968cc005)
![image](https://github.com/user-attachments/assets/ddf2bde7-7fb2-468a-9b59-0ffabc935bc9)
![image](https://github.com/user-attachments/assets/420b630b-4855-4c81-9b74-574631c0a7d3)
![image](https://github.com/user-attachments/assets/2c785f09-b17e-4eb3-8798-5e5b8035dc12)
![image](https://github.com/user-attachments/assets/8dea819c-382c-4616-831a-dd22ec68c261)




## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
