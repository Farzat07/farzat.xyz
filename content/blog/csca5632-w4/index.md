+++
title = "📰 Classifying BBC News Articles with Machine Learning"
description = "Using machine learning to automatically classify BBC news articles by topic—comparing unsupervised and supervised approaches to see which performs best."
date = 2025-10-31
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

In this project, I explored how machine learning can help categorize BBC news
articles into topics like **business**, **politics**, **sport**,
**entertainment**, and **tech**. The idea was to see how well different models
could understand the content of an article and assign it to the right
category—without any human input.

## Getting Started

The dataset comes from a Kaggle competition and includes a mix of labeled and
unlabeled articles. Before diving into modeling, I spent some time cleaning the
data—removing duplicates, checking for balance across categories, and making
sure everything was in the right format.

## Preprocessing the Text

To prepare the articles for analysis, I used a technique called TF-IDF, which
helps highlight the most meaningful words in each article. I also tried a few
tweaks, like replacing numbers with a placeholder, to see if that would improve
performance. Turns out, it didn’t help much—some numbers (like years) actually
carry useful context.

## Unsupervised Learning: Finding Patterns Without Labels

I started with an unsupervised approach using Non-negative Matrix Factorization
(NMF). This method doesn’t rely on labeled data—it just looks for patterns in
the text. Surprisingly, it did quite well, reaching around **91% accuracy**
after some tuning.

## Supervised Learning: Training with Labels

Next, I tried supervised models, which learn from labeled examples. I used
Logistic Regression and LinearSVC, and both performed even better than NMF.
With enough training data, they reached up to **97% accuracy**.

What stood out was how efficient LinearSVC was—it managed to get solid results
even with a smaller portion of the training data.

## Final Thoughts

This project was a great way to compare different approaches to text
classification. It showed that while unsupervised models can be useful,
supervised learning tends to be more accurate when labels are available. It
also highlighted how preprocessing choices can impact performance in subtle
ways.

If you're curious about the details, the full notebook is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="BBC News Classification notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/BBC-News-Classification-Kaggle-Mini-Project).
