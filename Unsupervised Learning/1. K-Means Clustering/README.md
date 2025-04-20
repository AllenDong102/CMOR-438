# K-Means Clustering

## Project Overview
This project applies the K-Means clustering algorithm to the MNIST Digits Dataset using scikit-learn. K-Means is an unsupervised learning technique that groups similar data points into clusters by minimizing intra-cluster variance.

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
   - Scaled features using `StandardScaler`
   - Applied PCA to reduce the dataset to 2 principal components for visualization

2. Model Training
   - Used `KMeans(n_clusters=10)` to fit the scaled data
   - Predicted cluster labels using the fitted model

3. Model Evaluation
   - Calculated:
     - Silhouette Score to measure intra-cluster cohesion
     - Adjusted Rand Index (ARI) to compare clustering with true digit labels
   - Visualized:
     - Cluster assignment in PCA-reduced 2D space
     - Confusion matrix of clusters vs true digit labels

## Results
### Performance Metrics
- Silhouette Score: 0.1356
- Adjusted Rand Index (ARI): 0.5305

### Visualizations
- PCA Scatter Plot: Showed moderate cluster separation with visible groupings for several digits.
- Confusion Matrix: Indicated clusters generally align with digit labels but with noticeable overlap.

---

## Analysis of Results

1. Clustering Performance
   - The silhouette score (0.1356) is relatively low, which is expected for high-dimensional data like digits. It suggests clusters aren't well-separated in the original feature space.
   - The ARI of 0.5305 indicates moderate agreement between the predicted clusters and true labels—reasonable for an unsupervised method on a complex task.

2. Cluster Behavior
   - Certain clusters (e.g., those aligned with digits 1, 3, 7, and 9) were more coherent.
   - Other digits (like 4, 8, and 9) overlapped more with neighboring clusters due to visual similarity in handwritten strokes.

3. Dimensionality Reduction Impact
   - PCA reduction to 2 dimensions aided in visualization but may have compressed some separability, affecting silhouette score.

4. Algorithm Characteristics
   - K-Means works best on convex, spherical clusters—its performance here is limited by the complex, high-dimensional structure of the digit data.
   - Nonetheless, it can still uncover meaningful groupings and serves as a strong baseline for clustering tasks.

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
jupyter notebook K-Means-Clustering.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
