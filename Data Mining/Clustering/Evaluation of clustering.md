# Cluster Evaluation methods

## External methods

1. Adjust Rand Index(ARI)
It measures the simlairty between the true labels and the labels assigned by the clustering algorithm. ARI values ranges from -1 to +1. A higher ARI value indeicate a better clustering.

	ARI = N - [a * b]/N / 1/2(a + b) - (a * b)/N
	
	where N: is the total number of point in cluster(pair of 2)
	a: is the total numebr of points in cluster with true labels
	b: is the total number of points in cluster with predicted labels by the algorithm

## Internal methods

1. Silhoutee
It measures the similarity of data points within the same cluster compared to data points in different clusters. A higher silhouette score indicates better clustering with value ranging from -1(poor clustering) to +1(well -seprated clustering).

2. Davies_bouldin index
It measures the average similarity(distance) between each cluster and its most similar cluster. A lower Davies_bouldin index indicates better clustering, with values closet to 0 suggesting more distinct and well seprated clusters.