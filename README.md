# Fashion-mnist_dataset_Clustering

### Overview

This project explores various clustering techniques on the Fashion MNIST dataset using different dimensionality reduction methods. The goal is to identify the best combination of clustering algorithm and dimensionality reduction technique based on specific performance metrics.

### Dataset

The dataset used is the [Fashion MNIST dataset](https://keras.io/api/datasets/fashion_mnist/), which consists of 70,000 grayscale images in 10 categories.

### Methodology

The methodology of this project involves several key steps to preprocess the data, reduce its dimensionality, and apply clustering techniques.

1. **Data Preprocessing**:
   
- **Flattening and Normalization**: Each image is converted into a flat array and normalized to prepare it for clustering.
- **Dimensionality Reduction**:
  - **Principal Component Analysis (PCA)**: Reduces the dataset from 784 dimensions to 187, preserving 95% of the variance in the data. PCA captures the main variance directions, simplifying the data and retaining significant information for clustering.
  - **Stacked Autoencoder (SAE)**: A neural network-based dimensionality reduction method that compresses the data to 32 dimensions through a series of encoding and decoding layers. SAE captures non-linear relationships in the data, making it suitable for complex image patterns.
    
2. **Clustering Algorithms**:
- **K-Means Clustering**: Partitions the dataset into distinct, non-overlapping subsets or clusters. Each cluster has a centroid, and the goal is to minimize the within-cluster variance.
- **MiniBatch KMeans**: A faster variant of K-Means that operates on small random samples, reducing computational time and making it ideal for large datasets.
  
3. **Performance Metrics**:
- **Calinski-Harabasz Index (CHI)**: Measures the density and separation of clusters, with higher values indicating better-defined clusters.
- **Davies-Bouldin Index (DBI)**: Evaluates cluster similarity, where lower values indicate more distinct clusters.
- **Silhouette Score**: Assesses how similar data points are to their own clusters compared to other clusters, ranging from -1 to 1 (higher scores indicate better-defined clusters).
  
### Results & Analysis
   
**Dimensionality Reduction Techniques**
- **PCA**: PCA achieves a balance between dimensionality reduction and variance retention (95%), reducing computation without losing significant information. However, clusters tend to be less distinct, as observed in the clustering metrics.
- **SAE**: SAE surpasses PCA in all performance metrics, demonstrating its effectiveness for capturing complex patterns in image data. Clustering results with SAE exhibit better-defined and more cohesive clusters.
  
**Clustering Algorithms**
- **MiniBatch KMeans**: This algorithm consistently shows lower training and execution times across all data types (Raw, PCA, SAE), making it highly efficient for large datasets. It is preferred when computational efficiency is a priority.
- **K-Means**: Though occasionally slower, K-Means provides slightly better clustering quality, as indicated by the Davies-Bouldin Index (DBI) and Silhouette Score, especially when paired with SAE.
  
**Optimal Configuration**
Combining SAE with K-Means yields the highest clustering quality:

- **Calinski-Harabasz Index**: Highest score (2250.13), indicating dense, well-separated clusters.
- **Davies-Bouldin Index**: Lowest score (1.57), showing minimal overlap and high intra-cluster cohesion.
- **Silhouette Score**: Highest score (0.20), reflecting good cluster separation and cohesion.

### Summary of Observations

- **SAE vs. PCA**: SAE consistently achieves better results across all metrics, proving more effective for this image clustering task.
- **Algorithm Efficiency**: MiniBatch KMeans is faster, but K-Means provides better-defined clusters.
- **Dimensionality Reduction Impact**: Both PCA and SAE improve clustering performance over raw data, but SAE provides the best overall cluster structure and separation.
  
This repository provides the code for implementing and evaluating these techniques on the Fashion-MNIST dataset. The findings highlight the value of combining deep learning-based dimensionality reduction with robust clustering algorithms for image data.
