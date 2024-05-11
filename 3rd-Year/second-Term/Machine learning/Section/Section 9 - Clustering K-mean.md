Let's break down the implementation of K-Means clustering using emojis and points:

1. **Imports and Setup**:
   - 📚 Import necessary libraries including matplotlib for visualization and modules from scikit-learn for dataset generation and K-Means clustering.

   ```python
   import matplotlib.pyplot as plt
   from sklearn.datasets import make_blobs
   from sklearn.cluster import KMeans
   ```

2. **Dataset Creation**:
   - 📊 Generate a synthetic dataset with 150 samples and 10 clusters using the `make_blobs` function.

   ```python
   # Create dataset
   x, _ = make_blobs(n_samples=150, centers=10)
   ```

3. **K-Means Clustering**:
   - 🎯 K-Means is an unsupervised machine learning algorithm used for clustering data points into groups or clusters based on their similarities.
   - 🔍 It partitions the data into K clusters where each data point belongs to the cluster with the nearest mean, serving as the prototype of the cluster.
   - 🏢 The algorithm iteratively assigns each data point to the nearest centroid and then recalculates the centroids as the mean of the data points assigned to each cluster.
   - 📊 The process continues until convergence, where the centroids no longer change significantly or a specified number of iterations is reached.
   - 💡 K-Means is sensitive to the initial placement of centroids and may converge to local optima, hence it's often recommended to run the algorithm multiple times with different initializations and choose the one with the lowest within-cluster variance.
   - 🎯 Initialize and fit the KMeans clustering algorithm with the desired number of clusters (10 in this case).
   - 🔍 Obtain cluster labels for each data point using the `fit_predict` method.
$$ \large \mu_k = \frac{1}{n_k} \sum_{i=1}^{n_k} x_i $$

   ```python
   # Perform KMeans clustering
   km = KMeans(n_clusters=10)
   cluster_labels = km.fit_predict(x)
   ```

4. **Visualization**:
   - 📊 Plot the clusters with data points and centroids.
   - 📌 Data points are represented by circles with cluster-specific colors.
   - ⭐ Centroids are represented by stars in red color.

   ```python
   # Plot clusters with centroids
   plt.scatter(x[:, 0], x[:, 1], c=cluster_labels, marker='o', edgecolor='black', s=50)
   plt.scatter(km.cluster_centers_[:, 0], km.cluster_centers_[:, 1], marker='*', c='red', s=200, edgecolor='black')
   plt.show()
   ```

![[K-Means Clustering.png]]