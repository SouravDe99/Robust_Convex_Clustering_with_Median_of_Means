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
This is how the output looks like:
```
k*,ari,nnmi
4,0.979428490191042,0.9204397662192251
4,0.9761196880837723,0.9118458794392409
4,0.9667183481830429,0.8879166706405104
4,0.9761196880837723,0.9118458794392409
4,0.9761196880837723,0.9118458794392409
4,0.9738558996587799,0.9053236443706584
4,0.9761196880837723,0.9118458794392409
5,0.9614211875735842,0.8648203280209935
4,0.9665433866026978,0.8870909574317797
4,0.9736821659514047,0.9060605455713794
4,0.9713315357349245,0.8992758407775359
5,0.962900257377943,0.8693911188978068
4,0.9667183481830429,0.8879166706405104
4,0.9532065217783168,0.8831960884636375

```

#2.  The folder "synthetic_testing" contains codes for algorithms to be run on real datasets. They include the functions to form the synthetic datasets. 
Below are some code blocks that you need to keep in mind while running the code:
```python
## Choose the set of hyperparameters you prefer
gamma = 50000 ## gamma parameter defined in the algorithm
mu = 3 ## mu parameter defined in the algorithm
k = 13 ## nearest neighbours parameter in k-NN
phi = 0.01
N = 500 ## Number of iterations
tol1 = 0.005 ## Tolerance parameter defined in the algorithm
tol2 = 0.5 ## Tolerance parameter defined in the algorithm
```
```python
## Uncomment the line corresponsing to the dataset you want to work on
# data, label = skd.make_blobs(n_samples = 500, random_state = 100) # tol1 = 0.01
data, label = skd.make_circles(n_samples = 250, factor = 0.25, noise = 0.05, random_state = 0) 
```
```python
for h in range(1): ## change this range to your desired range to get better approximations of the performance measures.

        ## Uncomment the desired line to choose the type of error you want to introduce
        #X, label_1 = add_noise(data, label_0, 0.05*m)
        X, label = add_noise_annulus(data, label_0 ,0.05, 0.35, 0.6)
        # X, label_1 = add_normal_noise(data, label_0, 0.3)
        #X, label = add_outlier(X, label_1, 0.1)
```

