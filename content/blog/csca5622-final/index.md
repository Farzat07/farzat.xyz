+++
title = "📧 Is This Spam? Testing Email Classification Models"
description = "Exploring which machine learning models best detect spam emails—and why ensemble methods like AdaBoost and Random Forest come out on top."
date = 2025-10-22
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

Spam filters are something we rely on every day, often without thinking about
how they work. In this project, I explored how different machine learning
models perform when tasked with identifying spam emails using a dataset from
the UCI Machine Learning Repository.

## About the Dataset

The dataset includes over 4,600 emails, each described by 57 features. These
features capture things like how often certain words or characters appear
(e.g., “free”, “$”, “!”), and how long sequences of capital letters are. Each
email is labeled as either spam or not spam.

Some features are surprisingly specific—like the presence of the word “george”
or the area code “650”—which turned out to be strong indicators of non-spam.
These quirks reflect the personal nature of the original email sources.

## What I Tried

The goal was to test a few different models and see which one did the best job.
I compared:

* Logistic Regression
* Random Forest
* AdaBoost
* Support Vector Machines (SVMs)

Each model was tuned to find the best settings, and then evaluated based on
accuracy, precision, and recall.

## What Worked Best

The ensemble models—Random Forest and AdaBoost—stood out. They consistently
delivered high accuracy and precision, outperforming the benchmarks published
on UCI’s website.

Logistic Regression also did well, especially when regularization was used to
handle overlapping features. SVMs, on the other hand, didn’t perform as
strongly. Interestingly, the simpler LinearSVC model did better than the more
complex RBF kernel version.

## Why Precision Matters

In spam detection, false positives (marking a legitimate email as spam) are
worse than false negatives. So precision is more important than raw accuracy.
Fortunately, the best-performing models had strong precision scores, especially
the ensemble ones.

## Final Thoughts

This project was a great way to see how different models handle a real-world
classification task. While the results were solid, there’s still room to
improve—especially when it comes to minimizing false positives. Adjusting
thresholds or tweaking model weights could help push precision even higher.

The full notebook with code and visualizations is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="Spam Email Classification notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/introduction-to-machine-learning-supervised-learning-final-assignment).
