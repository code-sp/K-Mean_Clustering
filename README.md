# Student performance analysis using K-Mean clustering algorithm

Data collection and Read Data:

We receive input as a CSV file. Each line represents an item, and it contains numerical values (one for each feature) split by commas. We will read the data from the file, saving it into an array. Each element of the array is another array containing the item values for the feature.




Initialize Mean:

We want to initialize each mean’s values in the range of the feature values of the items. For that, we need to find the min and max for each feature. The variables minima, maxima are arrays containing the min and max values of the items respectively. We initialize each mean’s feature values randomly between the corresponding minimum and maximum.




Euclidean Distance:

We will be using the Euclidean distance as a metric of similarity for our data, Euclidian distance because k-means minimizes within clusters variance and as per definition of variance it is identical to the sum of squared Euclidian distances from the center. The way k-means is constructed is not based on distances. K-means minimizes within-cluster variance


Update Means: 

To update a mean, we need to find the average value for its feature, for all the items in the mean/cluster. We can do this by adding all the values and then dividing by the number of items, or we can use a more elegant solution. We will calculate the new average without having to read all the values by: m = (m*(n-1)+x)/n

where m is the mean value for a feature, n is the number of items in the cluster and x is the feature value for the added item.


Classify Items: 

Now we need to write a function to classify an item to a group/cluster. For the given item, we will find its similarity to each mean.


Find means: 

To actually find the means, we will loop through all the items, classify them to their nearest cluster and update the cluster’s mean. We will repeat the process for some fixed number of iterations. If between two iterations no item changes classification, we stop the process as the algorithm has found the optimal solution. The below function takes as input k (the number of desired clusters), the items and the number of maximum iterations, and returns the means and the clusters.


Find Clusters: 

Finally, we want to find the clusters, given the means. We will iterate through all the items and we will classify each item to its closest cluster.
