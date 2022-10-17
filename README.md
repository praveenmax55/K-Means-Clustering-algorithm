# Implementation of K-Means Clustering Algorithm
## Aim
To write a python program to implement K-Means Clustering Algorithm.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation

## Algorithm:

### Step1
<br>import the necessary packages.

### Step2
<br>Read the csv file.

### Step3
<br>Scatter plot the applicant income and loan amount.

### Step4
<br>Obtain the kmean clustring for 2 classes.

### Step5
<br>Pretict the cluster group of Applicant Income and Loanamount.

## Program:
```python
#DEVELOPED BY: Aakash S
#REG NO: 21500657
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')

x1 = pd.read_csv('clustering.csv')
print(x1.head(2))
x2 = x1.loc[:, ['ApplicantIncome','LoanAmount']]
print(x2.head(2))

x = x2.values
sns.scatterplot(x[:,0], x[:,1])
plt.xlabel('Income')
plt.ylabel('Loan')
plt.show()

kmean =KMeans(n_clusters=4)
kmean.fit(x)

print('Clusters Centers:', kmean.cluster_centers_)
print('Labels:', kmean.labels_)

predicted_class = kmean.predict([[9000,120]])
print('The cluster group for Applicant Income 9000 and Loanamount 150 :' ,predicted_class)

```
## Output:
![output](./output1.png)

## Result
Thus the K-means clustering algorithm is implemented and predicted the cluster class using python program.