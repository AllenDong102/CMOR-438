# Random Forests

## Project Overview
This project applies the Random Forest algorithm to classify handwritten digits from the MNIST Digits Dataset using scikit-learn. Random Forests, being an ensemble of decision trees, enhance classification accuracy by reducing overfitting and improving generalization.

## Dataset Overview
### MNIST Digits Dataset
- Source: Scikit-learn (`datasets.load_digits()`)
- Description: The dataset contains 8x8 pixel grayscale images of handwritten digits (0-9).
- Attributes:
  - 64 features (each pixel intensity)
  - 10 classes (digits 0–9)
- Size:
  - Full dataset: 1,797 samples
  - Training set: 1,437 samples
  - Testing set: 360 samples

## Algorithm Implementation Steps
1. Data Preprocessing
   - Loaded and split the dataset into training and test sets
   - Standardized the features using `StandardScaler`

2. Model Training
   - Trained a `RandomForestClassifier` from scikit-learn
   - Applied Grid Search (`GridSearchCV`) to optimize hyperparameters:
     - `n_estimators`: Number of trees in the forest
     - `max_depth`: Maximum depth of trees
     - `max_features`: Maximum features considered at each split
   - Best parameters found: `n_estimators=200`, `max_depth=20`, `max_features='sqrt'`

3. Model Evaluation
   - Evaluated the model using:
     - Accuracy
     - Confusion Matrix
     - Classification Report
     - Feature Importance Visualization
     - Display of misclassified digit images

## Results
### Performance Metrics
- Test Accuracy: 96.11%

#### Classification Report
| Digit | Precision | Recall | F1-Score | Support |
|--------|-----------|--------|----------|---------|
| 0 | 0.97 | 0.97 | 0.97 | 36 |
| 1 | 0.90 | 0.97 | 0.93 | 36 |
| 2 | 1.00 | 0.97 | 0.99 | 35 |
| 3 | 0.97 | 0.97 | 0.97 | 37 |
| 4 | 0.97 | 0.97 | 0.97 | 36 |
| 5 | 0.97 | 1.00 | 0.99 | 37 |
| 6 | 1.00 | 0.97 | 0.99 | 36 |
| 7 | 0.92 | 1.00 | 0.96 | 36 |
| 8 | 0.94 | 0.86 | 0.90 | 35 |
| 9 | 0.97 | 0.92 | 0.94 | 36 |

- Macro Avg F1-Score: 0.96
- Weighted Avg F1-Score: 0.96

### Visualizations
- Confusion Matrix
- Feature Importance by Pixel Index
- Misclassified Digit Images

---

## Analysis of Results

1. Model Performance
   - The Random Forest achieved a strong accuracy of 96.11%, validating its effectiveness on the MNIST digit classification task.
   - Digits like 2, 5, and 6 achieved near-perfect classification, while digit 8 showed the most misclassifications.
   - The confusion matrix reveals some digit pairs that are easily confused—such as 8 with 1 or 7, and 9 with 3—indicating visual ambiguity in handwritten input.

2. Feature Importance
   - The feature importance plot demonstrates which pixel indices had the most influence on classification.
   - Important features are well-distributed across the digit grid, aligning with meaningful stroke patterns in digit images.

3. Misclassified Examples
   - Examples of misclassified digits highlight model limitations, particularly in ambiguous or poorly written digits.
   - The visualization provides intuitive insights into where the classifier struggles and how improvements might be made using deeper models or image augmentation.

4. Algorithm Characteristics
   - Random Forests excel at capturing non-linear patterns while avoiding overfitting.
   - Hyperparameter tuning with grid search further improved generalization and performance on test data.

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
jupyter notebook Random_Forests.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
