## Natural Language Processing (NLP) - Sentiment Analysis on IMDB Dataset of Movie Reviews
### Introduction
Natural Language Processing (NLP) is a field of Artificial Intelligence (AI) focused on the interaction between computers and human language. It involves the application of computational techniques to analyze and synthesize natural language and speech. One common NLP task is sentiment analysis, which aims to determine the sentiment expressed in a piece of text. This repository contains two projects that perform sentiment analysis on the IMDB movie reviews dataset using different algorithms: **Naive Bayes and Bidirectional LSTM.**
### Dataset
The IMDB movie review dataset contains 50,000 movie reviews, labeled as positive or negative. It is widely used for binary sentiment classification tasks. This dataset is ideal for demonstrating different NLP techniques for text classification.

Download the IMDB movie reviews dataset from Kaggle using the following links:

https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews

### Naive Bayes Classifier
**Data Loading and Preprocessing:**
* Load the dataset and clean the text by removing HTML tags, punctuation, and stopwords, and by lemmatizing words.
* Libraries used: **pandas,** **re,** **NLTK.**
  
  [![re](https://img.shields.io/badge/re-1f425f?style=for-the-badge)](https://docs.python.org/3/library/re.html)
 
  [![nltk](https://img.shields.io/badge/nltk-9cf?style=for-the-badge&logo=python&logoColor=white)](https://www.nltk.org/)
  
**Text Vectorization:**
* Convert text data into TF-IDF vectors.

**Model Training:**
* Split the data into training and testing sets.
* Train a Naive Bayes classifier.

**Model Evaluation:**
* Evaluate the model using accuracy, confusion matrix, and classification report.

### Bidirectional LSTM
**Data Loading and Preprocessing:**

**Text Representation:**
* Convert text data into sequences and pad them to ensure uniform length.
* Library used: **tensorflow.keras.preprocessing.sequence.**

**Model Building:**
* Build a Bidirectional LSTM model with embedding layers and dropout for regularization.

**Model Training:**
* Split the data into training and testing sets.
* Train the Bidirectional LSTM model.

**Model Evaluation:**

### Results
Naive Bayes Classifier achieved an accuracy of 85% while Bidirectional LSTM achieved an accuracy of 74%. 


