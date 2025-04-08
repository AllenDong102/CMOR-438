# Linear Regression

## Project Overview
This project implements Linear Regression to predict median house values in California based on economic and demographic factors. The model is evaluated using Mean Squared Error (MSE) and compared with scikit-learn's `LinearRegression` for benchmarking.

## Dataset Overview
### California Housing Dataset
- Source: `sklearn.datasets.fetch_california_housing()`
- Target Variable: `MedHouseVal` (Median house price in a neighborhood)
- Features:
  - `MedInc`: Median income in the neighborhood
  - `HouseAge`: Average age of houses
  - `AveRooms`: Average number of rooms per house
  - `AveBedrms`: Average number of bedrooms per house
  - `Population`: Neighborhood population
  - `AveOccup`: Average number of occupants per household
  - `Latitude`: Geographic latitude
  - `Longitude`: Geographic longitude
- Size: ~20,000 samples, 8 features

## Algorithm Implementation Steps
1. Data Preprocessing
   - Standardized feature values using StandardScaler for stable training
   - Split data into 80% training / 20% testing

2. Linear Regression Implementation
   - Defined a Linear Regression model using Gradient Descent
   - Implemented weight and bias updates using mathematical equations
   - Trained the model to minimize Mean Squared Error

3. Model Evaluation
   - Computed MSE for performance assessment
   - Compared results with Scikit-Learn's `LinearRegression` model


## Results
### Performance Metrics
| Model                     | Mean Squared Error (MSE) |
|---------------------------|--------------------------|
| Custom Linear Regression  | 0.5673                   |
| Scikit-Learn Linear Regression | 0.5559              |

---

### Analysis of Results

1. Model Performance
   - The custom Linear Regression model achieved a Mean Squared Error (MSE) of 0.5673, while the Scikit-Learn model slightly outperformed it with an MSE of 0.5559.
   - This small performance gap (~0.01) indicates that the custom implementation closely replicates the behavior of a professional-grade model, validating the correctness of the underlying algorithm and gradient descent optimization.

2. Prediction Accuracy
   - The Predicted vs Actual Prices plot shows that both models capture the general upward trend of housing prices relative to actual values.
   - The red dashed line indicates an ideal fit. The clustering of points around this line—especially for mid-range prices—shows decent predictive accuracy.
   - Slight deviations at the high and low ends suggest the models may underperform on extreme values, which is expected in simple linear models without regularization or feature engineering.

3. Residual Analysis
   - The Residuals Distribution plot displays a near-normal distribution centered around zero for both models, which suggests that the assumptions of linear regression (e.g., homoscedasticity and normality of errors) are reasonably satisfied.
   - The narrower shape and tighter peak of the Scikit-Learn residuals indicate slightly more consistent predictions, although the scratch model still exhibits strong behavior.

4. Interpretation
   - Given the low error values and visually normal residual distribution, we can conclude that the model has successfully captured the linear trends within the dataset.
   - More advanced techniques (e.g., regularization, feature transformations, or non-linear models) could further improve performance but are beyond the scope of basic linear regression.

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
jupyter notebook Linear_Regression.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
