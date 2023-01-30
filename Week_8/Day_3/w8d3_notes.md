# W8D3 notes

## Today

NLP I

## Lecture

### Topics

- Introduction to NLP
- Data Preparation
  - Stop words removal
  - Lemmatization
  - Stemming
  - Tokenization
- Text data representation
  - Bag of Words
  - TfIdf
  - Word2Vec

## Core

Bag of words - document classification

### [What is Natural Language?](https://data.compass.lighthouselabs.ca/days/w08d3/activities/705)

Article: [What Is Natural Language Processing?](https://machinelearningmastery.com/natural-language-processing/) Sept 22, 2017

- Natural language is human speech and text
- Linguistics is the scientific study of language

### [Introduction to NLP](https://data.compass.lighthouselabs.ca/days/w08d3/activities/706)

Article: [A Simple Introduction to Natural Language Processing](https://becominghuman.ai/a-simple-introduction-to-natural-language-processing-ea66a1747b32) Oct 15, 2018

> The ultimate objective of NLP is to read, decipher, understand, and make sense of the human languages in a manner that is valuable.

Functions:

- Translation
- Grammar checking
- Interactive Voice Response (call centres)
- Personal assistants

Techniques:

1. Syntax. grammar

- Lemmatization
- Morphological segmentation
- Word segmentation
- Part-of-speech tagging
- Parsing
- Sentence breaking
- Stemming

2. Semantics. meaning

- Named entity recognition
- Word sense disambiguation
- NL generation

### [Representations](https://data.compass.lighthouselabs.ca/days/w08d3/activities/710)

- Turning words into numbers
- Occurs after data cleaning

Article: [Fundamentals of Bag Of Words and TF-IDF](https://medium.com/analytics-vidhya/fundamentals-of-bag-of-words-and-tf-idf-9846d301ff22) Sep 4, 2019

- Bag of words
  - word frequency is a predictor
  - used in document classification
  - Uses a vocabulary
  - Sparse vectors of word count are created for each document, then euclidean distance determines document similarity
  - N-grams
    - Vocabulary is made of n-token sequence of words
- TF-IDF: term frequency-inverse document frequency
  - term frequency: count of a word in a document over the total words in the document
  - Inverse document frequency: log(total documents/count of docs containing word)
  - Rare words are important

>TF-IDF gives larger values for less frequent words in the document corpus. TF-IDF value is high when both IDF and TF values are high i.e the word is rare in the whole document but frequent in a document.

### [Word2Vec](https://data.compass.lighthouselabs.ca/days/w08d3/activities/712)

Article: [The Illustrated Word2vec](https://jalammar.github.io/illustrated-word2vec/) March 27, 2019

Similarity between vectors: cosine_similarity

Language model training

- a window of length n is slid across a text.
- Words 1 to n-1 are used as input and word n is the output
- Alternatives
  - Continuous Bag of Words:
    - input: words 1 to k-1 and k+1 to n
    - output: word k
  - skipgram:
    - input: word k
    - output: words 1 to k-1 and k+1 to n
  
Create word embeddings:

- give the probability that two words are neighbours (logistic regression)
- in the corpus used for training, all words are neighbours. Need to create examples of words that are not neighbours by randomly selecting from vocabulary (adding noise)

Skipgram with Negative Sampling (SGNS)

word2vec hyperparameters:

- window size
  - small window size (2-15): similarity scores indicate words are interchangeable (both antonyms and synonyms)
  - large window sizes (>15): similarity score indicates word relatedness
- number of negative samples
  - 2-5 is adequate for a large enough dataset
  - 5-20 recommended

### [RNN](https://data.compass.lighthouselabs.ca/days/w08d3/activities/717)

Word-level language model

- assign integer to each word

Character level language model

- assign an integer to each character
- Dataset contains a significant number of out-of-vocabulary words or infrequent words
- most text strings are short, and length bound
- long sequences may not capture long-range dependencies
- slower than word-level for same dataset
