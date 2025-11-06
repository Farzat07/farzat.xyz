+++
title = "🌪️ Classifying Disaster Tweets with Deep Learning"
description = "A comparative study of GRU and LSTM architectures for binary classification of disaster-related tweets."
date = 2025-11-03
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

## Project Overview

Social media platforms like Twitter often serve as early indicators of
real-world events. This project explores how machine learning can be used to
automatically classify tweets as either disaster-related or not—an application
with potential value for emergency response teams, journalists, and public
safety organizations.

The dataset comes from the Kaggle NLP with Disaster Tweets competition, and
includes over 7,600 labeled tweets. The challenge lies in the ambiguity of
language: disaster-related terms are often used metaphorically, making
classification non-trivial.

## Approach

The analysis began with a baseline model using metadata features (like location
and keywords), followed by a more advanced pipeline using text-based features
and pretrained GloVe embeddings. The text was cleaned and tokenized to align
with GloVe’s training conventions, and padded for input into recurrent neural
networks.

Two types of RNN architectures were explored:

* **LSTM (Long Short-Term Memory)**
* **GRU (Gated Recurrent Unit)**

Each was tested across multiple configurations, varying the number of layers,
units, and dropout rates. Early stopping and custom callbacks were used to
optimize for F1-score, which was chosen as the primary evaluation metric.

## Key Findings

* **GRU outperformed LSTM**, achieving an F1-score of **0.857** and an accuracy
of **88.2%**.
* **Dropout** helped reduce overfitting but significantly increased training
time due to limitations in GPU optimization.
* **Model performance fluctuated**, suggesting that randomness and training
dynamics played a larger role than expected.
* **Metadata alone** (via Random Forest) was insufficient, with an F1-score of
just **0.617**.

## Reflections

While GRU emerged as the best model, the results showed sensitivity to
hyperparameters and training conditions. Dropout and early stopping helped
mitigate overfitting, but the trade-offs in training time and reproducibility
were notable.

Future improvements could include:

* Exploring alternative regularization techniques
* Leveraging attention mechanisms or transformer-based models
* Incorporating tweet length and other linguistic features more explicitly

***

If you're curious about the details, the full notebook is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="NLP Disaster Tweets notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/Kaggle-Mini-Project-NLP-Disaster-Tweets).
