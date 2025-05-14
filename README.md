# Robust_Convex_Clustering_with_Median_of_Means
Codes for the paper "Convex Clustering Redefined: Robust Learning with the Median of Means Estimator".

Instructions : 
#1. The folder "real_testing" contains codes for algorithms to be run on real datasets. They include the links to the real datasets. They output a file that contains a sequence of ARI, AMI, and the estimated number of clusters for the dataset. These are useful for various tests and error rates provided in the main paper and the appendix.

```python
## This is an illustration of the comet_testing.ipynb file with additional comments
dataset = "newthyroid" ## choose the dataset name here
```
```python
## Choose the set of hyperparameters you prefer
n, d = data.shape
p = 0.1
gamma = 50000
mu = 100
k = 45
phi = 0.01
l = n // 20
b = n // l
N = 100
tol1 = 0.02
tol2 = 0.5

t = np.arange(n)
```
```python
## Here, set the desired directory where you want to save the output
file = open(dataset + ".csv", "a")
csvwriter = csv.writer(file)
for m in range(m):
    csvwriter.writerow([k_star[m], ari[m], nnmi[m]])
file.close()
```

#2.  The folder "synthetic_testing" contains codes for algorithms to be run on real datasets. They include the links to the synthetic datasets. They output a file that contains a sequence of ARI, AMI, and the estimated number of clusters for the dataset. These are useful for various tests and error rates provided in the main paper and the appendix.
