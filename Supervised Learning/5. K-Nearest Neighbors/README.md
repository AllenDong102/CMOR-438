# K-Nearest Neighbors

## Project Overview
This project implements the K-Nearest Neighbors (KNN) algorithm to classify handwritten digits (0-9) using the Digits Dataset from scikit-learn. The goal is to predict the correct digit based on an 8x8 grayscale image representation. KNN is a non-parametric, instance-based learning algorithm that classifies a data point based on the majority vote of its k-nearest neighbors.

## Dataset Overview
### Digits Dataset
- Source: Scikit-learn (`datasets.load_digits()`)
- Description: The dataset consists of images of handwritten digits (0-9), where each image is an 8x8 grid of pixel values
- Attributes:
  - 64 features (pixel intensity values)
  - 10 classes (digits 0 through 9)
- Size:
  - Training samples: 1,439
  - Testing samples: 360

## Algorithm Implementation Steps
1. Data Preprocessing
   - Loaded the dataset from scikit-learn
   - Standardized the features using StandardScaler to ensure fair distance comparisons
   - Split the dataset into 80% training and 20% testing for evaluation

2. Model Training
   - Implemented the KNN algorithm using scikit-learn's `KNeighborsClassifier`
   - Used cross-validation to determine the optimal value of k
   - Selected optimal k-value through grid search

3. Model Evaluation
   - Evaluated the model using:
     - Accuracy: Measures the proportion of correctly classified digits
     - Confusion Matrix: Shows the distribution of correct and incorrect predictions
     - Classification Report: Precision, recall, and F1-score for each digit class

## Results
### Performance Metrics
- Optimal k-value: 1
- Test Accuracy: 96.67%

#### Classification Report
| Digit | Precision | Recall | F1-Score | Support |
|--------|------------|------------|------------|------------|
| 0 | 1.00 | 1.00 | 1.00 | 36 |
| 1 | 0.92 | 0.97 | 0.95 | 36 |
| 2 | 0.97 | 0.97 | 0.97 | 35 |
| 3 | 0.97 | 1.00 | 0.99 | 37 |
| 4 | 0.97 | 0.94 | 0.96 | 36 |
| 5 | 0.97 | 1.00 | 0.99 | 37 |
| 6 | 0.97 | 1.00 | 0.99 | 36 |
| 7 | 0.95 | 0.97 | 0.96 | 36 |
| 8 | 0.94 | 0.89 | 0.91 | 35 |
| 9 | 1.00 | 0.92 | 0.96 | 36 |

### Visualizations
[Confusion Matrix Heatmap]
- Visualization of classification performance across all digit classes
- Highlights areas of confusion between digits

## Analysis of Results
1. Model Performance
   - The model achieved 96.67% accuracy on the test set, indicating high classification capability.
   - Digits such as 0, 3, 5, and 6 were classified perfectly.
   - Digit 8 showed the most frequent confusion, especially with digits 1 and 9, due to visual similarities in handwriting.
   - The macro and weighted F1-scores (0.97) show consistent performance across all digit classes.

2. Algorithm Characteristics
   - A low optimal `k=1` suggests that most digits lie very close to their true class neighbors in feature space.
   - Standardizing features played a key role in ensuring that all pixel values contributed equally to distance calculations.
   - Despite the simplicity of KNN, it proved to be a powerful baseline for image classification when the dataset is small and low-dimensional.

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure Python is installed with the necessary libraries:
```bash
pip install numpy matplotlib seaborn scikit-learn
```

### 3. Run the Jupyter Notebook
```bash
jupyter notebook K-Nearest_Neighbors.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
