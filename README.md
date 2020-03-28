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
- Consider a random sample (without replacement) of m<<n data points with members x(i). [Dubes and Jain](https://www.sciencedirect.com/science/article/pii/S1474667017633652) suggest choosing 5% of the data points so that the nearest-neighbor distances will be independent and thus approximate a Beta distribution.
- Generate a set Y of m uniformly randomly distributed data points.
- Define two distance measures,
    - u(i) the distance of y(i) in Y from its nearest neighbour in X, and
    - w(i) the distance of x(i) in X from its nearest neighbour in X.
    

{\displaystyle H={\frac {\sum _{i=1}^{m}{u_{i}^{d}}}{\sum _{i=1}^{m}{u_{i}^{d}}+\sum _{i=1}^{m}{w_{i}^{d}}}}\,}

