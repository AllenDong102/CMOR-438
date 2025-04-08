# Logistic Regression

## Project Overview
This project implements Logistic Regression from scratch to classify breast cancer tumors as benign or malignant using diagnostic features. The model is evaluated using accuracy, precision, recall, and F1-score and compared with scikit-learn's `LogisticRegression` for benchmarking.

## Dataset Overview
### Breast Cancer Wisconsin Dataset
- Source: `sklearn.datasets.load_breast_cancer()`
- Target Variable:
  - `0`: Benign Tumor
  - `1`: Malignant Tumor
- Features:
  - `mean radius`, `mean texture`, `mean perimeter`, `mean area`, `mean smoothness`
  - `worst radius`, `worst texture`, `worst perimeter`, `worst area`, `worst smoothness`
  - and 20+ other diagnostic measurements
- Size: 569 samples, 30 features

## Algorithm Implementation Steps
1. Data Preprocessing
   - Loaded dataset from `sklearn.datasets`
   - Standardized feature values using StandardScaler
   - Split data into 80% training / 20% testing

2. Logistic Regression Implementation
   - Defined a Logistic Regression model using Gradient Descent
   - Used Sigmoid Activation Function
   - Optimized using Binary Cross-Entropy Loss
   - Updated weights and bias using Gradient Descent

3. Model Evaluation
   - Computed Accuracy, Precision, Recall, and F1-score
   - Compared results with Scikit-Learn's `LogisticRegression` model

## Results
### Performance Metrics
| Model                        | Accuracy | Precision | Recall | F1-Score |
|-----------------------------|----------|-----------|--------|----------|
| Custom Logistic Regression  | 0.9912   | 0.9861    | 1.0000 | 0.9930   |
| Scikit-Learn Logistic Regression | 0.9737   | 0.9722    | 0.9859 | 0.9790   |

---

### Analysis of Results

1. Model Performance
   - The custom Logistic Regression model achieved near-perfect classification performance, with an accuracy of 99.12% and an F1-score of 0.9930.
   - In comparison, Scikit-Learn’s model scored slightly lower at 97.37% accuracy and 0.9790 F1-score. Both models are highly effective, but the scratch implementation even outperformed the benchmark in this case.
   - The custom model demonstrated perfect recall (1.0000), indicating that it correctly identified all malignant tumors without any false negatives—a critical factor in medical diagnosis scenarios.

2. Training Convergence
   - The loss curve shows a smooth, steep decline early in training, gradually flattening out, indicating effective learning and convergence over time.
   - The binary cross-entropy loss steadily decreases and stabilizes, suggesting that the gradient descent was properly implemented and the learning rate was appropriate.

3. Classification Behavior
   - The confusion matrix reveals just one misclassification: a benign tumor labeled as malignant. While this is a false positive, it is typically more acceptable than false negatives in cancer diagnosis.
   - The balance of precision (0.9861) and recall (1.0000) results in a strong F1-score, showcasing the model’s robustness and suitability for real-world binary classification tasks.

4. Algorithm Insight
   - The sigmoid activation function effectively transformed raw linear combinations into calibrated probability scores.
   - Feature scaling with `StandardScaler` contributed significantly to training stability and convergence.
   - Binary cross-entropy was well-suited as a loss function, providing meaningful gradients that improved the model with each epoch.

---

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure you have Python and required libraries installed:
```bash
pip install numpy matplotlib seaborn scikit-learn
```

### 3. Run the Notebook
```bash
jupyter notebook Logistic_Regression.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
