# Disaster Tweet Classification

## Overview
This project focuses on the challenge of identifying whether a given tweet is reporting a real-life disaster or not. In the era of real-time social media, quickly and accurately identifying emergency situations can be crucial for disaster relief and emergency response teams.

The project utilizes Natural Language Processing (NLP) techniques to clean, analyze, and classify tweets into two categories:
- **Disaster (1)**: The tweet refers to a real disaster.
- **Not Disaster (0)**: The tweet refers to something else (e.g., metaphorical use of disaster-related words).

## Methodology

### 1. Data Preprocessing
Raw tweet text is often noisy. The following steps were taken to clean the data:
- **Lowercasing**: Converting all text to lowercase for consistency.
- **URL Removal**: Removing web links that do not contribute to classification.
- **Noise Reduction**: Removing punctuation, special characters, and numbers.
- **Whitespace Normalization**: Cleaning up extra spaces.

### 2. Feature Engineering & Embeddings
- **Word2Vec**: Used Gensim to train word embeddings on the tweet corpus, allowing the model to capture semantic relationships between words (e.g., "bomb" and "detonated").
- **TF-IDF Vectorization**: Employed Term Frequency-Inverse Document Frequency (TF-IDF) with unigrams and bigrams to represent the importance of words relative to the entire dataset.

### 3. Machine Learning Model
- **Algorithm**: Logistic Regression with a balanced class weight to handle potential label imbalances.
- **Optimization**: Fine-tuned the regularization parameter (C) and adjusted the decision threshold to prioritize **Recall**.
- **Performance**: Achieved a validation recall of **0.8504** at a decision threshold of 0.4, ensuring that a high percentage of actual disaster tweets are correctly identified.

## Technologies Used
- **Python**
- **Pandas** for data manipulation
- **Scikit-learn** for machine learning and vectorization
- **Gensim** for Word2Vec embeddings
- **Jupyter Notebook** for interactive development

## Project Structure
- `Disaster_Tweet_Classification.ipynb`: The main Jupyter notebook containing the full data pipeline and model training.
- `DTC Data.zip`: Compressed dataset used for training and testing.
- `README.md`: Project documentation.

## How to Run
1. Ensure you have the required libraries installed:
   ```bash
   pip install pandas scikit-learn gensim
   ```
2. Unzip `DTC Data.zip` to extract the training and testing CSV files.
3. Open `Disaster_Tweet_Classification.ipynb` in Jupyter Notebook or Google Colab and run the cells.
