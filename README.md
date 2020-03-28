

# Hopkins-Statistic-Clustering-Tendency
A python implementation for computing the Hopkins' statistic [(Lawson and Jurs (1990))](https://pubs.acs.org/doi/abs/10.1021/ci00065a010) for measuring clustering tendency of data.

## Clustering Tendency
Cluster analysis or clustering is the task of grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar (in some sense) to each other than to those in other groups (clusters). 

However, clustering algorithms will locate and specify clusters in data even if none are present. It is therefore appropriate to measure the clustering tendency or randomness of a data set before subjecting it to a clustering algorithm.

To measure cluster tendency is to measure to what degree clusters exist in the data to be clustered, and may be performed as an initial test, before attempting clustering. 

## Hopkins' Statistic
Hopkins’ statistic is a simple measure of clustering tendency. It is based on the difference between the distance from a real point to its nearest neighbor, U, and the distance from a randomly chosen point within thedata space to the nearest real data point, W.  


## Algorithm 
- Let X be the set of n data points.
- Consider a random sample (without replacement) of m<<n data points with members <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a>. [Dubes and Jain](https://www.sciencedirect.com/science/article/pii/S1474667017633652) suggest choosing 5% of the data points so that the nearest-neighbor distances will be independent and thus approximate a Beta distribution.
- Generate a set Y of m uniformly randomly distributed data points.
- Define two distance measures,
    - <a href="https://www.codecogs.com/eqnedit.php?latex=u_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?u_{i}" title="u_{i}" /></a> the distance of <a href="https://www.codecogs.com/eqnedit.php?latex=y_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y_{i}" title="y_{i}" /></a> in Y from its nearest neighbour in X, and
    - <a href="https://www.codecogs.com/eqnedit.php?latex=w_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_{i}" title="w_{i}" /></a> the distance of <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> in X from its nearest neighbour in X.
- if the data is d dimensional, then the Hopkins statistic is defined as:

<a href="https://www.codecogs.com/eqnedit.php?latex=H&space;=&space;\frac{\sum_{i=1}^{m}&space;u_{i}^{d}}{\sum_{i=1}^{m}&space;u_{i}^{d}&space;&plus;&space;\sum_{i=1}^{m}&space;w_{i}^{d}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?H&space;=&space;\frac{\sum_{i=1}^{m}&space;u_{i}^{d}}{\sum_{i=1}^{m}&space;u_{i}^{d}&space;&plus;&space;\sum_{i=1}^{m}&space;w_{i}^{d}}" title="H = \frac{\sum_{i=1}^{m} u_{i}^{d}}{\sum_{i=1}^{m} u_{i}^{d} + \sum_{i=1}^{m} w_{i}^{d}}" /></a>

## Measuring Clustering Tendency with Hopkins' Statistic
If X were uniformly distributed, then <a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^{m}u_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^{m}u_{i}" title="\sum_{i=1}^{m}u_{i}" /></a>  and <a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^{m}w_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^{m}w_{i}" title="\sum_{i=1}^{m}w_{i}" /></a> would be close to each other, and thus H would be about 0.5. However, if clusters are present in D, then the distances for artificial points would be substantially larger than for the real ones in expectation, and thus the value of H will increase .

A value for H higher than 0.75 indicates a clustering tendency at the 90% confidence level.

The null and the alternative hypotheses are defined as follow:

- Null hypothesis: the data set X is uniformly distributed (i.e., no meaningful clusters)
- Alternative hypothesis: the data set X is not uniformly distributed (i.e., contains meaningful clusters)


- If the value is between {0.01, ...,0.3}, the data is regularly spaced.

- If the value is around 0.5, it is random.

- If the value is between {0.7, ..., 0.99}, it has a high tendency to cluster.
