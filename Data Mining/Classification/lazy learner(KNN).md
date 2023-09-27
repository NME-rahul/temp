# Lazy learners

These type of algorithm do not explictly learns on the dataset they just learns the data. when a new data point occurs they make prediction based on data distribution.

## K-nearest neighbour(KNN):-

KNN  algorithms finds the K-nearest data point in the training data set to th point based on similiarity sucha as Euclidean distance, the class with highest occurence in k-neighbours will be considered as class of unseen data.


Given a dataset with input features X and corresponding labels Y, and a unseen data x_new.

1. Calculate the euclidean distance between x_new and each data point in X.
2. Select k nearest neigbour(k points which have the lowest distance from x_new).
3. Count the K neighbours class.
4. Class having highest count will be consider as class of new data x_new.
