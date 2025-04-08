# Perceptron

## Project Overview
This project implements the Perceptron algorithm to classify breast cancer tumors as benign or malignant based on diagnostic features. The Perceptron, a linear classifier, learns a decision boundary to separate the two classes using labeled data.

Additionally, this project includes a benchmark comparison with scikit-learn's built-in `Perceptron` model to validate the custom implementation.

## Dataset Overview
### Breast Cancer Wisconsin Dataset
- Source: Built-in dataset from `scikit-learn`
- Description: Diagnostic data collected from breast cancer tumors, including mean, standard error, and worst values for various cell nuclei characteristics
- Attributes:
  - 30 features (e.g., radius, texture, smoothness, compactness, etc.)
  - Target variable: 
    - `1` for Benign tumors
    - `-1` for Malignant tumors

## Algorithm Implementation Steps
1. Data Preprocessing
   - Converted labels from `(0, 1)` to `(-1, 1)` for Perceptron training
   - Standardized feature values using StandardScaler to ensure all features contribute equally
   - Split the dataset into training and test sets (80% training, 20% testing)

2. Model Training
   - Implemented Perceptron algorithm from scratch
   - Trained the model to find a linear decision boundary that separates malignant from benign tumors

3. Model Evaluation
   - Evaluated the custom Perceptron's performance
   - Compared results with scikit-learn's built-in Perceptron to verify correctness

## Results
### Performance Metrics
| Metric                     | Value      |
|---------------------------|------------|
| Test Accuracy (Custom Perceptron) | ~93%    |
| Test Accuracy (Sklearn Perceptron) | ~98% |

## Analysis of Results
1. Model Performance
   - The custom Perceptron achieved a high accuracy (~93%), demonstrating effective learning of a linear boundary
   - The performance is comparable to scikit-learn's implementation, validating the correctness of the custom code
   - The slight difference in accuracy (~5%) between custom and sklearn implementations could be due to:
     - Different optimization parameters
     - Variations in the training process
     - Implementation details in the learning algorithm

2. Algorithm Characteristics
   - The Perceptron successfully learned a linear decision boundary
   - The high accuracy suggests that the breast cancer classification problem is largely linearly separable
   - The standardized features contributed to the model's performance by ensuring equal feature importance

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure you have Python and required libraries installed:
```bash
pip install numpy matplotlib scikit-learn
```

### 3. Run the Notebook
Open the notebook and execute all cells:
```bash
jupyter notebook Perceptron.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```