# Discretization-and-Binarization
# Why we used Discretization and Binarization
### Sometimes, numerical encoding is necessary to represent the data. Like we have data and one column the no.of downloads contains the values like 1020102, 203, 90, 32132323. It can't better plot the data on the graph. That's why we used Discretization and Binarization. 

# Methods
### (i) Discretization(binning)
### (ii) Binarization


# Discretization 
Discretization is a process of transforming continuous varaible into discrete variables by creating a set of contiguous interval that span the ranges of varaible values. Discretization also called bining where bin is a alternative name of interval.

Why we use?
### (i) To handle outliers
### (ii) To remove the values spread 


# Types of bining 
### (i) Supervised (Decision tree bining)
### (ii) Unsupervised (Equal width or uniform, Equal frequency quantile, K Means binning)
### (iii) Custom bining

### Equal width/ Uniform bining
### Equal width binning, also known as uniform binning or fixed-width binning, is a technique used to divide a numerical variable into a specified number of bins, where each bin has the same width or interval range.
### formuala max-min/bins
### Example
### import pandas as pd
### data = [10, 15, 20, 25, 30, 35, 40]
### num_bins = 3
### bin_width = (max(data) - min(data)) / num_bins
### bins = [min(data) + i * bin_width for i in range(num_bins + 1)]
### categories = pd.cut(data, bins)
### print(categories)
###Output
### [(10.0, 20.0], (10.0, 20.0], (10.0, 20.0], (20.0, 30.0], (20.0, 30.0], (30.0, 40.0], (30.0, 40.0]]
### Categories (3, interval[float64]): [(10.0, 20.0] < (20.0, 30.0] < (30.0, 40.0]]

### Equal frequency/ quantile binning corporates the percentage of total observations
### Quantile binning, also known as equal frequency binning or percentile binning, is a technique used to divide a numerical variable into bins based on the quantiles of the data.
### Example
### import pandas as pd
### data = [10, 15, 20, 25, 30, 35, 40]
### num_bins = 3
### categories = pd.qcut(data, q=num_bins, labels=False)
### print(categories)
### Output
### [0, 0, 1, 1, 2, 2, 2]
### Categories (3, int64): [0 < 1 < 2]

### K means binning used when our data in clusters
### K-means binning, also known as clustering-based binning, is a technique that uses the k-means clustering algorithm to group data points into bins based on their similarity. In k-means binning, the algorithm assigns each data point to the nearest centroid, creating distinct clusters. The cluster centers or centroids serve as the boundaries for the bins.


### from sklearn.cluster import KMeans
### data = [10, 15, 20, 25, 30, 35, 40]
### num_bins = 3
### kmeans = KMeans(n_clusters=num_bins)
### kmeans.fit(data)
### bin_labels = kmeans.predict(data)
### print(bin_labels)

### Custom Binning
### Custom binning refers to the process of creating bins or intervals for data that are tailored to specific requirements or domain knowledge. Instead of using a fixed number of equal-sized bins or predefined intervals, custom binning allows you to define bins based on your specific needs and insights about the data. In custom binning, you have control over the bin edges and can determine how to group the data values. This can be useful in various scenarios, such as when you want to emphasize certain ranges, account for outliers, or create bins based on specific business rules.

### Binarization
### In binarization convert continuous value into numerical value. For example, if your annual income is greater then six lac then you assign 0 otherwise you assign 1. Accoring to previous example if copy=True than  new column created otherwise changing occur in old column.  
