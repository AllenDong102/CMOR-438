# Principal Component Analysis

## Project Overview
This project demonstrates the use of Principal Component Analysis (PCA) on the MNIST Digits Dataset using scikit-learn. PCA is an unsupervised learning algorithm used for dimensionality reduction, feature extraction, and data visualization by projecting high-dimensional data into lower-dimensional subspaces while preserving the variance.

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
   - Loaded and scaled the dataset using `StandardScaler`

2. Dimensionality Reduction
   - Applied `PCA()` to the scaled data
   - Plotted the cumulative explained variance to determine the number of components needed to retain 90% of the variance
   - Projected data to:
     - 2 components (for 2D visualization)
     - 3 components (for 3D visualization)

3. Visualization
   - Plotted the dataset in 2D PCA space (color-coded by digit)
   - Visualized the PCA projection in 3D space
   - Displayed a cumulative variance plot showing how much variance each component contributes

## Results

### Performance Metrics
- Original data shape: (1797, 64)
- Number of components needed to retain 90% variance: ~21
- Cumulative Variance Curve: Visual inflection point observed around 20–25 components

### Visualizations
- Explained Variance Plot: Showed that ~90% variance is captured with the first 21 components
- 2D PCA Scatter Plot: Demonstrated that certain digits (like 0, 6, 8, 9) form relatively distinct clusters
- 3D PCA Scatter Plot: Improved spatial separation of digit clusters over 2D

---

## Analysis of Results

1. Dimensionality Reduction
   - PCA reduced the dataset from 64 to 2 or 3 dimensions for visualization while maintaining the majority of the information (~90% variance with 21 components).
   - This greatly simplifies downstream visualization and learning tasks.

2. Cluster Interpretability
   - Even in just 2D, the digits exhibit meaningful grouping.
   - Digits with distinct shapes (e.g., 0, 1, 6, 9) appear well-separated.
   - Overlap is expected for digits with similar shapes (e.g., 3 vs 5, 4 vs 9).

3. 3D Visualization
   - Adding a third component to the projection revealed more separation between classes.
   - A useful tool for both exploratory data analysis and semi-supervised learning setups.

4. PCA Characteristics
   - PCA is a linear technique: it performs best when variance is the most informative signal.
   - It works particularly well when high-dimensional data (like image pixels) has correlated features—as is the case with digit images.

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
jupyter notebook PCA.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
