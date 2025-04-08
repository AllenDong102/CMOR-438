# Decision Trees

## Project Overview
This project implements Decision Tree algorithms to solve both classification and regression problems. Two datasets are used:
1. The Breast Cancer Wisconsin Dataset for binary classification of tumor types (benign vs malignant).
2. The California Housing Dataset for predicting house prices using regression.

The decision tree classifier and regressor are evaluated based on classification accuracy, feature importance, and tree visualizations.

## Dataset Overview

### Breast Cancer Wisconsin Dataset
- Source: `sklearn.datasets.load_breast_cancer()`
- Shape: (569 samples, 30 features)
- Target:
  - `0`: Malignant tumor
  - `1`: Benign tumor

### California Housing Dataset
- Source: `sklearn.datasets.fetch_california_housing()`
- Shape: (20640 samples, 8 features)
- Target:
  - Median house value in a California district

## Algorithm Implementation Steps
1. Data Preprocessing
   - Loaded datasets and split into training and test sets
   - Standardized the feature values using `StandardScaler` for stable training
   - Handled both classification (binary target) and regression (continuous target)

2. Model Implementation
   - Used `DecisionTreeClassifier` for breast cancer classification
   - Used `DecisionTreeRegressor` for housing price prediction
   - Performed GridSearchCV to optimize tree parameters (e.g., `max_depth`, `min_samples_split`)
   - Visualized the decision trees and calculated feature importance

3. Model Evaluation
   - Classification performance measured using Accuracy, Confusion Matrix, and Classification Report
   - Regression model evaluated using visualization of the regression tree and interpretation of splits

## Results

### Breast Cancer Classification
- Accuracy: 0.9123
- Confusion Matrix:
  ```
  [[39,  3],
   [ 7, 65]]
  ```
- Classification Report:

  | Class | Precision | Recall | F1-score | Support |
  |-------|-----------|--------|----------|---------|
  | 0 (Malignant) | 0.85 | 0.93 | 0.89 | 42 |
  | 1 (Benign)    | 0.96 | 0.90 | 0.93 | 72 |

  - Macro Avg F1-score: 0.91  
  - Weighted Avg F1-score: 0.91  

- Best Parameters: `max_depth=5`, `min_samples_split=5`

### California Housing Regression
- Visualized the learned regression tree
- Interpreted branching logic with `MedInc`, `AveOccup`, and `Latitude` as key features

---

## Analysis of Results

1. Breast Cancer Classification
   - The decision tree model achieved 91.23% accuracy with high precision (0.85–0.96) and recall (0.90–0.93).
   - The confusion matrix shows minimal misclassification, and the model balances sensitivity and specificity well.
   - Feature importance analysis highlighted `worst radius`, `worst texture`, and `worst concave points` as most influential in prediction.

2. Model Visualization
   - The classification decision tree shows interpretable splits based on relevant features and Gini impurity values.
   - This allows for medical interpretability and traceability of classification decisions.

3. California Housing Regression
   - The regression tree revealed that median income (`MedInc`) and average occupancy (`AveOccup`) are critical determinants of housing prices.
   - Although regression performance was not numerically reported, the visualization clearly shows meaningful split logic and relationships.

4. General Insight
   - Decision Trees provide both predictive power and interpretability, making them valuable tools in both healthcare and real estate domains.
   - Limiting the depth and splitting threshold (via grid search) prevents overfitting and enhances generalization.

---

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure Python and required libraries are installed:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

### 3. Run the Notebook
```bash
jupyter notebook Decision_Trees.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
