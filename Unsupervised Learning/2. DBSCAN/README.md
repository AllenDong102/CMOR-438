# DBSCAN

## Project Overview
This project applies the DBSCAN (Density-Based Spatial Clustering of Applications with Noise) algorithm to the MNIST Digits Dataset using scikit-learn. DBSCAN is a density-based clustering technique that identifies core samples of high density and expands clusters from them, making it robust to noise and capable of discovering arbitrarily shaped clusters.

## Dataset Overview
### MNIST Digits Dataset
- Source: Scikit-learn (`datasets.load_digits()`)
- Description: The dataset contains 8x8 pixel grayscale images of handwritten digits (0-9).
- Attributes:
  - 64 features (each pixel intensity)
  - 10 classes (digits 0–9)
- Size:
  - Full dataset: 1,797 samples

## Algorithm Implementation Steps
1. Data Preprocessing
   - Standardized features using `StandardScaler`
   - Applied PCA to reduce data to 10 dimensions for clustering and 2 dimensions for visualization

2. Model Training
   - Applied `DBSCAN` with parameters `eps=2.0` and `min_samples=5` to the 10D PCA-reduced data
   - Automatically identified the number of clusters without needing to pre-specify `k`

3. Model Evaluation
   - Counted the number of clusters and noise points
   - Evaluated clustering quality using:
     - Silhouette Score (excluding noise points)
     - Adjusted Rand Index (ARI) to compare with true digit labels

## Results
### Performance Metrics
- Estimated Number of Clusters: 17
- Noise Points Detected: 558
- Silhouette Score: 0.1504
- Adjusted Rand Index (ARI): 0.2750

### Visualizations
- PCA Scatter Plot: DBSCAN clusters (colored), noise points (gray)
- Confusion Matrix: Cluster labels vs. true digit labels

---

## Analysis of Results

1. Clustering Performance
   - DBSCAN detected 17 clusters and marked 558 points as noise (~31% of the dataset).
   - The silhouette score (0.1504) is relatively low due to overlapping digit shapes and high dimensionality.
   - ARI of 0.2750 reflects modest alignment with true labels—reasonable given DBSCAN's unsupervised nature and noisy input.

2. Cluster Behavior
   - Several clusters align well with individual digits, but some digit classes are fragmented across clusters.
   - Digits like 1, 3, and 7 showed more coherent clustering; others (like 0, 5, 6) were spread out or confused with neighbors.

3. DBSCAN Strengths and Tradeoffs
   - Successfully detects noise/outliers, distinguishing it from K-Means and other partitioning methods.
   - Performs well with non-convex shapes and varied density, but is sensitive to `eps` and dimensionality.

4. Recommendations for Improvement
   - Try increasing `eps` (e.g., 2.5 or 3.0) to reduce noise and better merge sparse clusters.
   - Experiment with UMAP instead of PCA for dimensionality reduction.
   - Consider other clustering methods like Gaussian Mixture Models or Agglomerative Clustering for comparison.

---

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure Python and necessary libraries are installed:
```bash
pip install numpy matplotlib seaborn scikit-learn
```

### 3. Run the Notebook
```bash
jupyter notebook DBSCAN.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
