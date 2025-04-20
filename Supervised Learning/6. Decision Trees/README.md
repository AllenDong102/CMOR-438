# **Decision Trees**

## **Project Overview**
This project implements Decision Tree algorithms to solve both classification and regression problems. Two datasets are used:
1. The Breast Cancer Wisconsin Dataset for binary classification of tumor types (benign vs malignant).
2. The California Housing Dataset for predicting house prices using regression.
The decision tree classifier and regressor are evaluated based on classification accuracy, feature importance, learned rules, and tree visualizations.

---

## **Dataset Overview**

### **Breast Cancer Wisconsin Dataset**
- **Source**: `sklearn.datasets.load_breast_cancer()`
- **Shape**: (569 samples, 30 features)
- **Target**:
  - `0`: Malignant tumor
  - `1`: Benign tumor

### **California Housing Dataset**
- **Source**: `sklearn.datasets.fetch_california_housing()`
- **Shape**: (20640 samples, 8 features)
- **Target**:
  - Median house value in a California district

---

## **Algorithm Implementation Steps**

### **1️⃣ Data Preprocessing**
- Loaded datasets and split into training and test sets.
- Standardized the feature values using `StandardScaler` for stable training.
- Handled both classification (binary target) and regression (continuous target).

### **2️⃣ Model Implementation**
- Used `DecisionTreeClassifier` with a fixed `max_depth` for interpretable classification.
- Used `DecisionTreeRegressor` for regression with visual inspection of splits.
- Exported rules from the decision tree to improve model interpretability.
- Visualized tree structures using `plot_tree`.

### **3️⃣ Model Evaluation**
- **Classification**: Accuracy, Confusion Matrix, Classification Report.
- **Regression**: Mean Squared Error (MSE), R² score.

---

## **Results**

### **Breast Cancer Classification**
- **Accuracy**: 0.9123
- **Confusion Matrix**:
  ```
  [[39,  3],
   [ 7, 65]]
  ```
- **Classification Report**:

  | Class | Precision | Recall | F1-score | Support |
  |-------|-----------|--------|----------|---------|
  | 0 (Malignant) | 0.85 | 0.93 | 0.89 | 42 |
  | 1 (Benign)    | 0.96 | 0.90 | 0.93 | 72 |

  - **Macro Avg F1-score**: 0.91  
  - **Weighted Avg F1-score**: 0.91  

- **Best Parameters**: `max_depth=5`, `min_samples_split=5`

### **Decision Tree Rules**
```
|--- worst radius <= 0.13
|   |--- worst concave points <= 0.33
|   |   |--- area error <= 1.25
|   |   |   |--- area error <= -0.02
|   |   |   |   |--- smoothness error <= -1.21
|   |   |   |   |   |--- class: 1
|   |   |   |   |--- smoothness error >  -1.21
|   |   |   |   |   |--- class: 1
|   |   |   |--- area error >  -0.02
|   |   |   |   |--- texture error <= 1.38
|   |   |   |   |   |--- class: 1
|   |   |   |   |--- texture error >  1.38
|   |   |   |   |   |--- class: 0
|   |   |--- area error >  1.25
|   |   |   |--- class: 0
|   |--- worst concave points >  0.33
|   |   |--- worst texture <= -0.00
|   |   |   |--- worst smoothness <= 2.05
|   |   |   |   |--- worst area <= -0.09
|   |   |   |   |   |--- class: 1
|   |   |   |   |--- worst area >  -0.09
|   |   |   |   |   |--- class: 0
|   |   |   |--- worst smoothness >  2.05
|   |   |   |   |--- class: 0
...
|   |   |   |   |--- class: 0
|   |   |--- worst concavity >  -0.40
|   |   |   |--- class: 0
```

---

### **California Housing Regression**
- **MSE**: _Reported in Notebook_
- **R² Score**: _Reported in Notebook_
- Median income (`MedInc`) and average occupancy (`AveOccup`) are key predictive features.
- Tree visualization provides clear interpretations of learned patterns.

---

## **Analysis of Results**

### **1️⃣ Breast Cancer Classification**
- The decision tree classifier achieved high accuracy (~91%) with excellent precision and recall.
- Tree rules provide transparency in decision-making, aiding medical trust and interpretability.

### **2️⃣ Tree Rules**
- Using `export_text`, the model exposes its logic in if-else format.
- Clear thresholds on features like `worst concave points`, `area error`, and `smoothness error` aid in understanding the model's decision process.

### **3️⃣ Housing Regression**
- The regression tree exposes how `MedInc` and `Latitude` influence predictions.
- Tree depth control avoids overfitting, balancing complexity and performance.

---

## ⚙ **How to Run the Project**

### **1. Clone the Repository**
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### **2. Install Dependencies**
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

### **3. Run the Notebook**
```bash
jupyter notebook Decision_Trees.ipynb
```

Or use Google Colab:
```markdown
- Upload the notebook to Colab
- Run all cells
```