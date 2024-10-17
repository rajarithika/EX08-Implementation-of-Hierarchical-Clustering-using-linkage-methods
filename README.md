# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Compute the distance between every pair of data points,resulting in a distance matrix.
2.Assign each data point to its own individual cluster. 
3.Using a linkage criterion,find the two closest cluster and merge them. 
4.Visualize the hierarchical clustering as a dendrogram.



## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: Raja rithika
RegisterNumber:  2305001029
*/
import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 from scipy.cluster.hierarchy import dendrogram, linkage, fcluster # Changed 'dendog
 from sklearn.preprocessing import StandardScaler
 df=pd.read_csv('/content/Hclus_EX8.csv')
 df.head()
 X=df[['StudentID','Marks']].values
 X
 #Perform hierarchical clustering (agglomerative)
 Z=linkage(X, method='complete')
 #Plot dendogram
 plt.figure(figsize=(5,2))
 plt.title("Dendogram for Student Segmentation")
 labels=range(1,len(df)+1)
 dendrogram(Z,labels=labels)
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 #Cut the dendrogram to form clusters(let's say we want 5 clusters)
 max_clusters=2
 clusters=fcluster(Z,max_clusters,criterion='maxclust')
 clusters
 #Scatter plot with different colors for each cluster
 plt.figure(figsize=(5,2))
 plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
 plt.title("Student segmented (Hierarchical Clustering)")
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 Z=linkage(X, method='single')
 #Plot dendogram
 plt.figure(figsize=(5,2))
 plt.title("Dendogram for Student Segmentation")
 labels=range(1,len(df)+1)
 dendrogram(Z,labels=labels)
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()
 #Cut the dendrogram to form clusters(let's say we want 5 clusters)
 max_clusters=2
 clusters=fcluster(Z,max_clusters,criterion='maxclust')
 clusters
 #Scatter plot with different colors for each cluster
 plt.figure(figsize=(5,2))
 plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
 plt.title("Student segmented (Hierarchical Clustering)")
 plt.xlabel("Student ID")
 plt.ylabel("Marks")
 plt.show()

```

## Output:
![image](https://github.com/user-attachments/assets/8ed9269c-66b9-4d8b-8a4e-9ef2c1699fb4)
![image](https://github.com/user-attachments/assets/38849de5-51d5-4c32-872e-b751f2db30bf)
![image](https://github.com/user-attachments/assets/1a8c1db0-a266-470d-9702-7a2ec63cb7c0)
![image](https://github.com/user-attachments/assets/1aabe96e-ea6e-43b3-a795-937ac4ecd9e6)
![image](https://github.com/user-attachments/assets/e1dbb632-f4ba-465b-b14b-2a052c76fb1d)






## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
