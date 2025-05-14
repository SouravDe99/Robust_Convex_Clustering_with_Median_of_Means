# Robust_Convex_Clustering_with_Median_of_Means
Codes for the paper "Convex Clustering Redefined: Robust Learning with the Median of Means Estimator".

Instructions : 
#1. The folder "real_testing" contains codes for algorithms to be run on real datasets. They include the links to the real datasets. They output a file that contains a sequence of ARI, AMI, and the estimated number of clusters for the dataset. These are useful for various tests and error rates provided in the main paper and the appendix. Below are some code blocks that you need to keep in mind while running the code:

```python
## This is an illustration of the comet_testing.ipynb file with additional comments
dataset = "newthyroid" ## choose the dataset name here
```
```python
## Choose the set of hyperparameters you prefer
n, d = data.shape ## n = number of datapoints, d = dimension of data
p = 0.1 ## noise % in fraction
gamma = 50000 ## gamma parameter defined in the algorithm
mu = 100 ## mu parameter defined in the algorithm
k = 45 ## nearest neighbours parameter in k-NN
phi = 0.01 
l = n // 20 ## Number of bins
b = n // l ## Number of elements in a bin
N = 100 ## Number of iterations
tol1 = 0.02 ## Tolerance parameter defined in the algorithm
tol2 = 0.5 ## Tolerance parameter defined in the algorithm

t = np.arange(n)
```
```python
## Here, you can set the desired directory where you want to save the output.
## The output is saved as dataset.csv (in this case, newthyroid.csv)
file = open(dataset + ".csv", "a")
csvwriter = csv.writer(file)
for m in range(m):
    csvwriter.writerow([k_star[m], ari[m], nnmi[m]])
file.close()
```
```
This is how the output looks like
![image](https://github.com/user-attachments/assets/ec1259cf-b7d5-4ccd-b0d8-95feb953f079)

```

#2.  The folder "synthetic_testing" contains codes for algorithms to be run on real datasets. They include the links to the synthetic datasets. 
