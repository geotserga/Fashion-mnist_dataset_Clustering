# Fashion-mnist_dataset_Clustering

### Overview

This project explores various clustering techniques on the Fashion MNIST dataset using different dimensionality reduction methods. The goal is to identify the best combination of clustering algorithm and dimensionality reduction technique based on specific performance metrics.

### Dataset

The dataset used is the Fashion MNIST dataset, which consists of 70,000 grayscale images in 10 categories.

### Methodology

The methodology of this project involves several key steps to preprocess the data, reduce its dimensionality, and apply clustering techniques. Initially, the images from the Fashion MNIST dataset are preprocessed by flattening them into one-dimensional arrays and normalizing the pixel values. This step ensures uniformity and prepares the data for further analysis.

Dimensionality reduction is then applied using two distinct methods to enhance the efficiency and effectiveness of the clustering algorithms. The first method is Principal Component Analysis (PCA), which reduces the dimensionality of the dataset to 187 components while retaining 95% of the original variance. PCA helps in simplifying the dataset while preserving the most important features. The second method is a Stacked Autoencoder (SAE), a type of neural network designed to learn efficient codings of the input data. The SAE compresses the data into a lower-dimensional space of 32 dimensions through a series of three encoding and three decoding layers, capturing more complex structures and patterns within the data.

Once the dimensionality reduction is completed, two clustering algorithms are employed to group the data into clusters. MiniBatchKMeans is the first algorithm used; it processes small, random samples of the dataset, significantly reducing computation time while maintaining clustering quality. This makes it particularly suitable for large datasets. The second algorithm is the traditional K-Means Clustering, which partitions the dataset into K distinct, non-overlapping subsets or clusters. Both algorithms aim to minimize the variance within each cluster and maximize the variance between clusters.

To evaluate the effectiveness of the clustering, several performance metrics are utilized. The Calinski-Harabasz Index measures the ratio of between-cluster dispersion to within-cluster dispersion, providing insight into the clustering's overall quality. The Silhouette Score assesses how similar an object is to its own cluster compared to other clusters, thus measuring cohesion and separation. The Davies-Bouldin Index calculates the average similarity ratio of each cluster with the cluster most similar to it, indicating the clarity and distinctness of the clusters.

These steps collectively provide a comprehensive approach to clustering the Fashion MNIST dataset, from preprocessing and dimensionality reduction to the application and evaluation of clustering algorithms. This methodology ensures a robust analysis and insightful results.
