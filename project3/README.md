IMDB Movie Reviews Sentiment Classification
Project Overview
This project focuses on sentiment classification of IMDB movie reviews as positive or negative using various machine learning and deep learning approaches. The pipeline includes preprocessing, feature engineering, and training multiple models, ranging from logistic regression to BERT, to evaluate performance differences.

Table of Contents
Project Overview
Data Preprocessing
Models and Results
Baseline Model
Logistic Regression
LightGBM
BERT
Custom Reviews
Conclusions
Data Preprocessing
To prepare the data for model training, reviews were cleaned and normalized using multiple methods:

Lowercasing and punctuation removal: Ensured uniformity in text.
Stopword removal: Removed irrelevant words (e.g., "the," "is").
Lemmatization: Used spaCy to reduce words to their base forms.
Implementation Example
python
Copy code
# spaCy-based cleaning function
def spacy_clean_text(text):
    doc = nlp(text)
    tokens = [token.lemma_ for token in doc if not token.is_stop and not token.is_punct and not token.is_digit]
    return ' '.join(tokens)
Models and Results
Baseline Model
A constant model that predicted the most frequent class in the training data served as a baseline:

Accuracy: 50.15%
F1 Score: 0.00
ROC AUC: 0.50
Logistic Regression
Logistic Regression (TF-IDF + spaCy)
Preprocessing: Text was cleaned using spaCy, then transformed using TF-IDF vectorization.
Results:
Accuracy: 85.62%
F1 Score: 85.75%
ROC AUC: 85.62%
LightGBM
LightGBM (TF-IDF + spaCy)
Preprocessing: Text cleaned with spaCy and vectorized using TF-IDF.
Results:
Accuracy: 84.04%
F1 Score: 84.14%
ROC AUC: 84.04%
BERT
Preprocessing: Text tokenized using BERT tokenizer, padded/truncated to a maximum length of 128 tokens.
Training: BERT fine-tuned with gradient checkpointing and gradient accumulation to optimize memory usage.
Results:
Epochs: 2
Training Loss: Reduced from 0.0949 to 0.0026
Validation Loss: Reduced from 0.0419 to 0.0015
Custom Reviews
The trained models were tested on custom reviews to validate real-world applicability.


Reviews and Predictions
Review	Logistic Regression	LightGBM
"This movie was amazing, I loved it!"	Positive	Positive
"The plot was horrible and acting worse"	Negative	Negative


Conclusions
This project demonstrates the evolution of sentiment classification from simpler machine learning models to transformer-based approaches. Key findings include:

Baseline Model: Served as a useful benchmark with limited predictive power.
Logistic Regression: Achieved high accuracy and balanced performance, making it effective for quick and interpretable results.
LightGBM: Slightly lower accuracy but faster training for high-dimensional data.
BERT: Outperformed traditional models by leveraging deep contextual embeddings.
Future Work
Experiment with hyperparameter tuning for BERT to optimize performance further.
Test on larger datasets or real-world review data for scalability.
