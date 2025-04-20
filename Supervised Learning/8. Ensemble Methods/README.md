# Ensemble Methods

## Project Overview
This project applies three ensemble learning techniques—Hard Voting, Bagging, and Boosting—to classify handwritten digits from the MNIST Digits Dataset using scikit-learn. These ensemble methods combine multiple base learners to enhance predictive performance and generalization.

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
   - Loaded the dataset and split into training and test sets (80/20 stratified split)

2. Model Training
   - Hard Voting: Combined predictions from Logistic Regression, Decision Tree, and K-Nearest Neighbors using majority vote.
   - Bagging: Trained 100 Decision Trees using bootstrapped subsets of data.
   - Boosting:
     - Gradient Boosting: Sequentially trained trees to correct previous errors.
     - Improved AdaBoost: Used deeper base estimators (depth=3) for better handling of digit variation.

3. Model Evaluation
   - Evaluated each model using:
     - Accuracy
     - Confusion Matrix
     - Classification Report

## Results
### Performance Metrics

| Method            | Accuracy |
|-------------------|----------|
| Hard Voting       | 96.94%   |
| Bagging           | 92.50%   |
| AdaBoost (Improved) | 94.17%   |
| Gradient Boosting | 95.56%   |

#### Example: Classification Report (Hard Voting)
| Digit | Precision | Recall | F1-Score | Support |
|--------|-----------|--------|----------|---------|
| 0 | 1.00 | 1.00 | 1.00 | 36 |
| 1 | 0.88 | 0.97 | 0.92 | 36 |
| 2 | 1.00 | 1.00 | 1.00 | 35 |
| 3 | 0.97 | 1.00 | 0.99 | 37 |
| 4 | 0.95 | 1.00 | 0.97 | 36 |
| 5 | 0.97 | 1.00 | 0.99 | 37 |
| 6 | 1.00 | 0.97 | 0.99 | 36 |
| 7 | 1.00 | 1.00 | 1.00 | 36 |
| 8 | 0.94 | 0.83 | 0.88 | 35 |
| 9 | 1.00 | 0.92 | 0.96 | 36 |

- Macro Avg F1-Score: 0.97
- Weighted Avg F1-Score: 0.97

### Visualizations
- Confusion Matrices for each method
- Misclassified Digit Image Visualizations (optional in notebook)

---

## Analysis of Results

1. Hard Voting:
   - Excellent performance (96.94%), combining the strengths of multiple diverse classifiers.
   - Achieved the best results overall.

2. Bagging:
   - Performed well (92.50%), though slightly worse than boosting methods.
   - More prone to instability with misclassifications around digits like 8 and 9.

3. Improved AdaBoost:
   - Upgraded base learner from depth=1 to depth=3 improved accuracy significantly to 94.17%.
   - Previously underperformed (~48%) with too shallow trees.

4. Gradient Boosting:
   - Very strong performance (95.56%), rivaling Hard Voting.
   - Excels in fine-grained error correction.

5. Common Error Patterns:
   - Digits 8 and 9 are commonly confused with similar-looking digits.
   - Feature intensity patterns show ambiguity in handwritten samples.

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
jupyter notebook Ensemble_Methods.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
