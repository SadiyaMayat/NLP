## Natural Language Processing (NLP) 
### Introduction
Natural Language Processing (NLP) is a field of Artificial Intelligence (AI) focused on the interaction between computers and human language. It involves the application of computational techniques to analyze and synthesize natural language and speech. It encompasses tasks such as text classification, machine translation, named entity recognition, sentiment analysis, question answering, text generation, speech recognition, information extraction, summarization, and language modeling. 

For more details https://www.deeplearning.ai/resources/natural-language-processing/

##  1. Sentiment Analysis on IMDB Dataset of Movie Reviews
### Dataset
The IMDB movie review dataset contains 50,000 movie reviews, labeled as positive or negative. It is widely used for binary sentiment classification tasks. This dataset is ideal for demonstrating different NLP techniques for text classification.

Download the IMDB movie reviews dataset from Kaggle using the following links:

https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews

### I. Naive Bayes Classifier
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

### II. Bidirectional LSTM
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

## 2. Machine Translation by Seq2Seq Model
### Encoder-Decoder LSTM
The encoder-decoder model is a neural network architecture commonly used in sequence-to-sequence tasks such as machine translation, text summarization, and speech recognition. It consists of two main components:

**1. Encoder:** This part of the model processes the input sequence (e.g., a sentence in the source language) and encodes it into a fixed-length context vector. The encoder typically consists of a series of recurrent neural networks (RNNs), long short-term memory networks (LSTMs), or gated recurrent units (GRUs) that capture the input sequence's semantic information.

**2. Decoder:** The decoder takes the context vector generated by the encoder and generates the output sequence (e.g., a sentence in the target language). Like the encoder, the decoder usually comprises RNNs, LSTMs, or GRUs and produces the output one token at a time, using the context vector and previously generated tokens as inputs.

To understand the architecture of Model: https://pradeep-dhote9.medium.com/seq2seq-encoder-decoder-lstm-model-1a1c9a43bbac

### Dataset
The sample data can be downloaded at [manythings.org](http://www.manythings.org/bilingual/) and comes from [Tatoeba](https://tatoeba.org/en). It is composed of sentence pairs in the language you need. In our case, I have used **Hindi-English** pairs.

### Summary of Code
**Data Loading and Preprocessing:**
* Reads the Hindi-English sentence pairs from a file.
* Cleans sentences by converting to lowercase and removing punctuation.
* Adds start and end tokens to English sentences.
* Tokenizes the sentences and converts them to sequences of integers.
  
**Tokenization and Padding:**
* Tokenizes Hindi and English sentences and calculates vocabulary sizes.
* Pads the sequences to ensure uniform input length.
  
**Model Building:**
* Constructs an encoder-decoder architecture with the following layers:
* **Encoder:** Embedding layer followed by an LSTM layer with dropout.
* **Decoder:** Embedding layer, LSTM layer with dropout, and a TimeDistributed Dense layer with softmax activation to predict the English translation.
  
**Model Compilation and Training:**
* Compiles the model using sparse categorical cross-entropy loss and the Adam optimizer.
*- Prepares data for [teacher forcing](https://machinelearningmastery.com/teacher-forcing-for-recurrent-neural-networks/) by shifting English sequences.
* Trains the model on the padded Hindi-English sequences for 100 epochs with a batch size of 64 and a 20% validation split.
  
**Prediction and Evaluation:**
* Defines a function to convert predicted logits to readable sentences.
* Evaluates the model by predicting the English translation of a given Hindi sentence and prints the original and predicted sentences.

### Reference
https://towardsdatascience.com/how-to-build-an-encoder-decoder-translation-model-using-lstm-with-python-and-keras-a31e9d864b9b
