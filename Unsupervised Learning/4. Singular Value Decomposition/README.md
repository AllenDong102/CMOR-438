# Singular Value Decomposition

## Project Overview
This project applies Singular Value Decomposition (SVD) to grayscale digit images from the MNIST Digits Dataset to demonstrate the power of low-rank matrix approximation. Using SVD, we can compress image data while preserving its structure, and analyze how many singular values are needed for a faithful reconstruction.

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
   - Loaded digit images from Scikit-learn
   - Selected individual 8x8 images for decomposition

2. Matrix Decomposition
   - Applied NumPy's `np.linalg.svd` to decompose each image as `U @ S @ V^T`
   - Reconstructed images using only the top `k` singular values for various values of `k` (1, 5, 10, 20)

3. Evaluation and Visualization
   - Compared reconstructed images visually to the original
   - Plotted reconstruction error (Frobenius norm) vs. number of singular values

## Results

### Visualizations
- Original vs Reconstructed Digits:
  - k = 1: Barely recognizable digit, mostly coarse structure
  - k = 5: Major structure preserved, fine detail slightly blurred
  - k = 10: Very close to original, almost indistinguishable
  - k = 20: Near-perfect reconstruction

- Error Curve:
  - Frobenius norm error drops sharply as `k` increases
  - Plateau begins around `k = 7`, showing diminishing returns

---

## Analysis of Results

1. Compression Effectiveness
   - Most of the visual information in digit images is captured by only a few singular values
   - This validates SVD as a powerful tool for image compression

2. Low-Rank Approximation
   - The rank of an 8x8 image is at most 8, and most digits can be well-approximated with even fewer singular values
   - Reconstruction quality improves significantly up to ~k = 7, then levels off

3. Error vs Rank
   - The reconstruction error plot clearly shows the diminishing returns of higher-rank approximations
   - Great for demonstrating energy retention in early components

4. Applications
   - SVD can be used in broader contexts like noise reduction, matrix completion, and data compression
   - Especially helpful when working with large image datasets or collaborative filtering tasks

---

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure Python and necessary libraries are installed:
```bash
pip install numpy matplotlib scikit-learn
```

### 3. Run the Notebook
```bash
jupyter notebook SVD.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
