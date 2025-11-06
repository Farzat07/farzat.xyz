+++
title = "🌸 Clustering Iris Species with K-Means and Hierarchical Methods"
description = "A hands-on comparison of K-Means and Agglomerative Clustering on the Iris dataset, with insights into performance, parameter tuning, and practical trade-offs."
date = 2025-11-01
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

## Why Clustering?

Clustering is a foundational technique in unsupervised learning, used to
uncover patterns in data without predefined labels. This project explores how
two popular clustering algorithms—**K-Means** and **Agglomerative Hierarchical
Clustering**—perform on the well-known **Iris flower dataset**, aiming to group
samples by species based solely on their morphological features.

***

## About the Dataset

The Iris dataset contains **150 samples** from three species: *setosa*,
*versicolor*, and *virginica*. Each sample includes four features:

* Sepal length
* Sepal width
* Petal length
* Petal width

While *setosa* is linearly separable, *versicolor* and *virginica* overlap
significantly, making this dataset ideal for testing clustering algorithms.

***

## What Was Explored

The analysis focused on:

* Comparing **K-Means** and **Agglomerative Clustering**
* Evaluating performance using **accuracy**, **silhouette score**, and
**Adjusted Rand Index (ARI)**
* Testing different **linkage methods** and **distance metrics**
* Visualizing clusters and errors using **PCA**

***

## Key Experiments & Findings

### Dimensionality Reduction with PCA

* **95.8%** of the variance was captured using just **2 principal components**, confirming
strong correlations among features—especially between petal length and width.

### Optimal Cluster Count

* Using metrics like **inertia**, **silhouette score**, and **accuracy**, the optimal
number of clusters was found to be **3**, matching the true number of species.

### Parameter Tuning for Agglomerative Clustering

* Tried combinations of:
  * Linkage: `ward`, `complete`, `average`, `single`
  * Metrics: `euclidean`, `manhattan`, `cosine`
* **Best result**: `average linkage` with `manhattan distance` achieved **88.7%
accuracy**, outperforming default settings.

### Performance Comparison

| Algorithm               | Accuracy | Silhouette Score | ARI  |
| ----------------------- | :------: | :--------------: | :--: |
| K-Means                 | 83.3%    | 0.46             | 0.62 |
| Agglomerative (default) | 82.7%    | 0.45             | 0.61 |
| Agglomerative (best)    | 88.7%    | 0.45             | 0.72 |

***

## Error Analysis

* **Setosa** was classified almost perfectly across all methods.
* Most errors occurred between **versicolor** and **virginica**, confirming
their overlapping nature.
* Agglomerative Clustering showed **bias** depending on parameters—sometimes
misclassifying one species more than the other.

***

## Final Thoughts

While Agglomerative Clustering achieved the highest accuracy with tuned
parameters, its **sensitivity to configuration** and **instability** in cluster
composition make it less reliable for real-world applications without labeled
data.

**K-Means**, despite slightly lower accuracy, offered **more balanced results**
and **greater stability**, making it a safer choice for practical clustering
tasks.

***

## Future Work

* Extend analysis to other clustering algorithms like DBSCAN or Spectral Clustering
* Apply to more complex datasets
* Explore automated parameter tuning techniques

***

The full notebook with code and visualizations is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="Iris Species Clustering Analysis notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/Unsupervised-Learning-Final-Project-Iris-Species-Clustering-Analysis).
