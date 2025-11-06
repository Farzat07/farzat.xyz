+++
title = "🧬 Detecting Cancer in Histopathology Images with CNNs"
description = "A practical deep learning project for binary classification using the PatchCamelyon dataset."
date = 2025-11-02
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

## Overview

This project explores the use of convolutional neural networks (CNNs) to detect
metastatic cancer in histopathologic images of lymph node tissue. The task is
framed as a binary classification problem, distinguishing between cancerous and
non-cancerous image patches.

The dataset, sourced from the PatchCamelyon (PCam) benchmark, offers a
realistic simulation of the challenges faced by pathologists. With over 220,000
labeled 96x96 RGB image patches, it strikes a balance between complexity and
computational feasibility—making it ideal for experimentation on a single GPU.

## Approach

The workflow began with a thorough exploratory data analysis to understand the
dataset’s structure, class distribution, and pixel intensity characteristics.
Data augmentation and normalization were applied to improve generalization and
training efficiency.

A flexible CNN builder was implemented to test different architectures—ranging
from simple to deeper and wider networks. After identifying the best-performing
architecture, various regularization techniques were evaluated, including L1/L2
penalties, dropout, and batch normalization.

To ensure fair comparisons and mitigate overfitting, training was supported by
callbacks such as early stopping, learning rate scheduling, and model
checkpointing.

## Results

The deeper CNN architecture consistently outperformed the others, achieving a
validation AUC of **0.9331**. Among regularization strategies, **additional
batch normalization** provided the best boost in performance, pushing the final
model’s validation AUC to **0.9878** when trained on the full dataset.

The final model demonstrated strong generalization, with balanced precision and
recall across both classes. Predictions on the test set were generated and
compiled into a submission-ready format.

## Reflections

While the performance metrics are promising, the project also highlighted some
challenges—particularly the variability in validation scores during early
training. This variability diminished with larger datasets and longer training,
suggesting that data volume plays a key role in stabilizing model performance.

Future work could explore more advanced architectures, ensemble methods, or
semi-supervised learning to further improve robustness and accuracy.

***

If you're curious about the details, the full notebook is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="CNN Cancer Detection notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/Kaggle-Mini-Project-CNN-Cancer-Detection).
