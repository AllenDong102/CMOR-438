# Neural Networks

## Project Overview
This project implements a Bidirectional LSTM-based Neural Network to classify movie reviews from the IMDB dataset as positive or negative. The model learns text patterns using word embeddings and recurrent layers to achieve high classification accuracy.

## Dataset Overview
### IMDB Movie Reviews Dataset
- Source: `keras.datasets.imdb`
- Task: Binary Sentiment Classification (Positive vs. Negative)
- Attributes:
  - Reviews: Preprocessed movie reviews (converted to word index format)
  - Sentiment Labels:
    - `0`: Negative review
    - `1`: Positive review
- Size: 50,000 reviews (25,000 training, 25,000 testing)

## Algorithm Implementation Steps
1. Data Preprocessing
   - Loaded dataset using `keras.datasets.imdb`
   - Converted text into numeric sequences (word index format)
   - Applied padding to ensure all sequences have the same length
   - Split into 80% training / 20% testing

2. Model Architecture
   - Embedding Layer: Converts words into dense vector representations
   - Bidirectional LSTM Layer: Captures sequential dependencies in both directions
   - Dropout Layers: Prevents overfitting by randomly disabling neurons
   - Dense Layers: Fully connected layers for classification
   - Output Layer: Uses sigmoid activation for binary classification

   #### Neural Network Structure
   | Layer | Type | Parameters |
   |--------|------------|------------|
   | Embedding | Converts words to dense vectors | 256-dim embeddings |
   | Bidirectional LSTM | Captures context from both directions | 64 units |
   | Dropout | Regularization | 30% dropout |
   | Dense (ReLU) | Fully connected | 32 neurons |
   | Dropout | Regularization | 30% dropout |
   | Dense (Sigmoid) | Output for classification | 1 neuron |

3. Model Training
   - Trained for 15 epochs with a batch size of 64
   - Used Binary Cross-Entropy Loss
   - Optimized using Adam (learning rate = 0.0005)

4. Model Evaluation
   - Evaluated using Accuracy, Precision, Recall, and F1-score
   - Compared training vs. validation loss to check for overfitting

## Results
### Performance Metrics
| Metric | Training | Validation | Test Set |
|--------|----------|------------|----------|
| Accuracy | 0.99 | 0.83 | 0.83 |
| Precision | 0.84 | 0.83 | 0.83 |
| Recall | 0.82 | 0.83 | 0.83 |
| F1-Score | 0.83 | 0.83 | 0.83 |

---

### Analysis of Results

1. Model Performance
   - The model achieved extremely high accuracy on the training set (99.42%), confirming that it was able to learn the underlying patterns in the data.
   - On the validation and test sets, the accuracy was 83.01%, with all other metrics (precision, recall, F1-score) around 0.83, reflecting a well-balanced and solid performance on unseen data.
   - This consistency across precision and recall shows that the model is not biased toward a specific class.

2. Overfitting Analysis
   - The training accuracy increased steadily, while validation accuracy plateaued early, and validation loss increased after a few epochs—this suggests mild overfitting after epoch 4 or 5.
   - Despite this, the model generalizes well enough due to dropout layers and regularization.

3. Classification Behavior
   - The confusion matrix shows that both classes are well-represented, and there’s no significant bias toward false positives or false negatives.
   - Predictions are relatively evenly distributed across both positive and negative sentiments, indicating that the bidirectional LSTM is capturing complex patterns effectively.

4. Architectural Insight
   - Bidirectional LSTM layers helped the model understand sentiment context from both directions of a review.
   - The embedding layer enabled semantic richness in word representation, crucial for text classification tasks.
   - The dropout layers played a key role in controlling overfitting while allowing the model to maintain high accuracy.

---

## How to Run the Project
### 1. Clone the Repository
```bash
git clone https://github.com/AllenDong102/CMOR-438.git
```

### 2. Install Dependencies
Ensure Python and required libraries are installed:
```bash
pip install numpy tensorflow keras seaborn matplotlib scikit-learn
```

### 3. Run the Notebook
```bash
jupyter notebook Neural_Network.ipynb
```

Or via Google Colab:
```markdown
- Upload notebook to Google Colab
- Run all cells sequentially
```
