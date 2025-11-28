### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE:12/04/2025 
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```
# Visitor segmentation based on characteristics
import pandas as pd
import matplotlib.pyplot as plt

# Read the data
df = pd.read_csv('/content/clustervisitor.csv')

# Define age groups
age_groups = {
    'Young ': (df['Age'] <= 30) ,
    'Middle': (df['Age'] >= 31) & (df['Age'] <= 60),
    'Old': (df['Age'] > 61)
}

# Count visitors in each age group
visitor_counts = []
for group in age_groups:
    count = df[age_groups[group]].shape[0]
    visitor_counts.append(count)

```# Plotting
age_group_labels = list(age_groups.keys())

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/4ed47362-7714-423c-9b09-d057df7c3b12)

### Program2:
```
df=pd.read_csv("clustervisitor(Salary).csv")
df1=df['Age']
df2=df['Salary']
df3=pd.concat([df1,df2],axis=1)
df3

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

sc=StandardScaler()
scaleddata=sc.fit_transform(df3)
print(scaleddata)

kmeans=KMeans(n_clusters=3,random_state=42)
df3['cluster']=kmeans.fit_predict(df3)
df3

import matplotlib.pyplot as plt

plt.scatter(df3['Age'], df3['Salary'], c=df3['cluster'])
plt.xlabel("Age")
plt.ylabel("Income (in thousands)")
plt.show()
```

### Output:
<img width="756" height="554" alt="image" src="https://github.com/user-attachments/assets/e9d36a64-0c4a-4be8-9efd-b2075866544a" />


### Result:
Hence Cluster and Visitor Segmentation for Navigation patterns in Python is implemented.
