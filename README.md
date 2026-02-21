# Buddy-Session

### 1. **Principal Component Analysis (PCA)**

* **Type:** Linear

* **Goal:** Maximize variance (captures the directions of greatest variance in the data).

* **How it works:**

  * PCA transforms the data into a set of orthogonal axes (principal components), ordered by the amount of variance each axis explains.
  * The first few principal components typically capture most of the variance, making it effective for dimensionality reduction.
  * Linear method; assumes data is approximately Gaussian.

* **Advantages:**

  * Simple and fast.
  * Reduces dimensionality by finding the principal components.
  * Makes data easier to visualize (e.g., projecting to 2D or 3D for plotting).

* **Use Cases:**

  * Preprocessing for machine learning.
  * Data compression.
  * Exploratory data analysis.

* **Limitations:**

  * Assumes linear relationships between features.
  * May not capture non-linear structures in the data.

---

### 2. **Linear Discriminant Analysis (LDA)**

* **Type:** Linear and **Supervised**

* **Goal:** Maximize class separability (finds linear combinations of features that separate classes).

* **How it works:**

  * LDA works similarly to PCA but adds the constraint that the components should maximize the separation between classes while minimizing within-class variance.
  * It's a supervised method that requires labeled data, unlike PCA, which is unsupervised.

* **Advantages:**

  * Useful for classification tasks.
  * Helps improve classifier performance by reducing dimensions while retaining class discriminability.

* **Use Cases:**

  * Classification problems.
  * Face recognition (dimensionality reduction with class separation).
  * Speech recognition.

* **Limitations:**

  * Assumes normal distribution of data within each class and identical covariance between classes.
  * Only works when you have class labels.

---

### 3. **Independent Component Analysis (ICA)**

* **Type:** Linear

* **Goal:** Find statistically independent components (as opposed to uncorrelated components in PCA).

* **How it works:**

  * ICA seeks to separate mixed signals into their original independent sources.
  * Unlike PCA, ICA looks for components that are statistically independent, which makes it useful for tasks like blind source separation.

* **Advantages:**

  * Captures more independent features compared to PCA.
  * Works well for problems like separating mixed audio signals (e.g., in speech processing or EEG signals).

* **Use Cases:**

  * Audio signal processing.
  * EEG and brain wave analysis.
  * Image or text source separation.

* **Limitations:**

  * More computationally intensive than PCA.
  * Assumes that the independent sources are non-Gaussian.

---

### 4. **t-Distributed Stochastic Neighbor Embedding (t-SNE)**

* **Type:** Non-linear and **Unsupervised**

* **Goal:** Preserve local structure in data for visualization in 2D or 3D.

* **How it works:**

  * t-SNE minimizes the divergence between probability distributions that represent pairwise similarities between data points in high and low-dimensional spaces.
  * It focuses on preserving local relationships rather than global structures.

* **Advantages:**

  * Excellent for visualizing high-dimensional data in 2D or 3D.
  * Often used in exploratory data analysis (EDA), especially for clusters and patterns.

* **Use Cases:**

  * Visualizing complex data (e.g., gene expression data, word embeddings).
  * Discovering underlying structure in high-dimensional datasets.
  * Data clustering and pattern recognition.

* **Limitations:**

  * Computationally expensive for large datasets.
  * It’s primarily used for visualization, not as a preprocessing step for machine learning.
  * Does not preserve global structure well.

---

### 5. **Multidimensional Scaling (MDS)**

* **Type:** Non-linear and **Unsupervised**

* **Goal:** Preserve pairwise distances between data points in lower dimensions.

* **How it works:**

  * MDS seeks to place data points in a lower-dimensional space while maintaining the pairwise distances between them as much as possible.
  * Two types: **classical MDS** (based on distance matrices) and **metric MDS** (works with continuous data).

* **Advantages:**

  * Works well when you have a similarity or distance matrix.
  * Can handle different kinds of distance measures.

* **Use Cases:**

  * Visualization of distance/similarity matrices.
  * Exploratory data analysis of distance-based data.
  * Understanding relationships between objects based on pairwise distances.

* **Limitations:**

  * Computationally expensive for large datasets.
  * Does not preserve global structure as well as some other methods.

---

### 6. **Uniform Manifold Approximation and Projection (UMAP)**

* **Type:** Non-linear and **Unsupervised**

* **Goal:** Preserve both local and global structures of data.

* **How it works:**

  * UMAP constructs a graph from the data, maintaining both local and global structure, and then optimizes this graph to project the data into a lower-dimensional space.
  * Based on manifold learning and topological data analysis.

* **Advantages:**

  * Much faster than t-SNE on large datasets.
  * Preserves both local and global structure, making it better than t-SNE for many real-world applications.
  * Scalable and works well with large datasets.

* **Use Cases:**

  * Data visualization (like t-SNE, but faster and more scalable).
  * Clustering.
  * Reducing dimensionality for machine learning.

* **Limitations:**

  * May not always produce as clean results as t-SNE when it comes to complex data (though generally better).
  * Still an emerging method compared to older techniques like PCA.

---

### **Comparison Summary**

| **Algorithm** | **Type**                 | **Goal**                                 | **Advantages**                                            | **Limitations**                                                    |
| ------------- | ------------------------ | ---------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ |
| **PCA**       | Linear                   | Maximize variance                        | Simple, fast, effective for large datasets                | Assumes linear relationships, not good for complex structures      |
| **LDA**       | Linear, Supervised       | Maximize class separability              | Useful for classification, class separation               | Assumes normal distribution, works only with labeled data          |
| **ICA**       | Linear                   | Find independent components              | Good for source separation (audio, EEG)                   | Assumes non-Gaussian sources, computationally expensive            |
| **t-SNE**     | Non-linear, Unsupervised | Preserve local structure                 | Excellent for visualization of high-dimensional data      | Slow for large datasets, does not preserve global structure well   |
| **MDS**       | Non-linear, Unsupervised | Preserve pairwise distances              | Works well with distance/similarity matrices              | Computationally expensive, does not preserve global structure well |
| **UMAP**      | Non-linear, Unsupervised | Preserve both local and global structure | Faster and scalable than t-SNE, better for large datasets | May not produce as clean results for very complex data             |

---

### **Key Takeaways:**

* **Linear Methods (PCA, LDA, ICA)** are great when the data relationships are linear or you need to preserve variance (PCA), maximize class separation (LDA), or separate independent sources (ICA).
* **Non-linear Methods (t-SNE, MDS, UMAP)** excel at capturing complex relationships and visualizing high-dimensional data, with **UMAP** being faster and better at preserving both local and global structure compared to **t-SNE**.
* **PCA** is best for simple and fast dimensionality reduction with high-dimensional data, while **t-SNE** and **UMAP** are often used for visualization.
* **LDA** is highly suited for supervised classification tasks, while **ICA** shines in situations like blind source separation.
