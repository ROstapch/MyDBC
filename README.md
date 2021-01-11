# MyDBC
My density baced clustering algorithm

It requires maximum distance between points as only parameter. On return you get a class with few main values, represented as numpy array

    density - can be used to plot initial density. Can be usefull when evaluating the data before automated clustering, to estimate number of clusters.
    cluster_labels - main value representing cluster labels for each data point after algorithm runs. It has labels for each step of algorithm, which stops when all points are recognized as abnormal and are set to label -1. That means that cluster_labels[0] will contain initial clusters, and cluster_labels[-1] will have all cluster labels set to -1.
    neighbors - has different data for each step of algorithm, same as cluster_labels. It has indexes of neighbors for each data point. No point in neighbors[-1] will have a neighbor.

Main idea of algorithm is so that initial clusters are set based on distance(distance between points is counted using euclidian metrics, but can be changed if needed) between points, that is passed in as a parameter. Further reclustering is done after marking points with least deinsity as abnormal. Density threshold value is increased each iteration.
