IMDB Movie Reviews Sentiment Classification
This project focuses on sentiment classification of IMDB movie reviews as positive or negative using various machine learning and deep learning approaches. The pipeline includes preprocessing, feature engineering, and training multiple models, ranging from logistic regression to BERT, to evaluate performance differences.

Table of Contents
Introduction
Data Preprocessing
Models and Results
Baseline Model
Logistic Regression
LightGBM
BERT
Custom Reviews
Conclusions
Introduction
The goal of this project is to build a robust sentiment analysis system for IMDB movie reviews. By testing both traditional machine learning and transformer-based deep learning models, we aim to demonstrate the effectiveness of modern approaches in natural language processing tasks.

Data Preprocessing
To prepare the data for modeling, the following preprocessing steps were applied:

Cleaning: Lowercasing, punctuation removal, and stopword elimination.
Lemmatization: Text normalization using spaCy for better feature representation.
Tokenization and Vectorization:
TF-IDF for traditional models.
BERT Tokenizer for transformer-based models.
Sample Code for Cleaning
python
Copy code
def spacy_clean_text(text):
    doc = nlp(text)
    tokens = [token.lemma_ for token in doc if not token.is_stop and not token.is_punct and not token.is_digit]
    return ' '.join(tokens)
Models and Results
Baseline Model
A constant model that predicts the most frequent class:

Accuracy: 50.15%
F1 Score: 0.00
ROC AUC: 0.50
Logistic Regression
Using spaCy for text cleaning and TF-IDF for feature extraction:

Accuracy: 85.62%
F1 Score: 85.75%
ROC AUC: 85.62%
LightGBM
Another traditional approach leveraging LightGBM with TF-IDF features:

Accuracy: 84.04%
F1 Score: 84.14%
ROC AUC: 84.04%
BERT
A pre-trained transformer model fine-tuned on the IMDB dataset:

Preprocessing: Tokenization, padding, and truncation to a maximum length of 128 tokens.
Training: Fine-tuned for 2 epochs with gradient checkpointing to reduce memory usage.
Results:
Training Loss: Reduced from 0.0949 to 0.0026.
Validation Loss: Reduced from 0.0419 to 0.0015.
Custom Reviews
The trained models were tested on new reviews to verify real-world applicability.

Example Reviews and Predictions
Review	Logistic Regression	LightGBM
"This movie was amazing, I loved it!"	Positive	Positive
"The plot was horrible and acting worse"	Negative	Negative
Conclusions
Baseline Model: Simple but ineffective as a benchmark.
Logistic Regression: High accuracy and reliable performance.
LightGBM: Comparable results to Logistic Regression, with faster training.
BERT: Demonstrated superior performance due to its deep contextual embeddings.
Future Work
Optimize BERT with hyperparameter tuning.
Test on larger datasets or deploy the model in real-world scenarios.
