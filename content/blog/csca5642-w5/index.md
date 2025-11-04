+++
title = "🎨 From Photos to Monet: CycleGAN and Styled CycleGAN for Artistic Style Transfer"
description = "Exploring GAN-based architectures to transform real-world photos into Monet-inspired paintings, with custom enhancements for better style fidelity."
date = 2025-11-04
[taxonomies]
tags = ["machine_learning"]
[extra]
styles = ["notebooks.css", ]
+++

## Project Overview

Art and AI intersect in this project, which tackles the Kaggle challenge *“I’m
Something of a Painter Myself.”* The goal: generate Monet-style images. Instead
of creating paintings from scratch, I focused on **style
transfer**—transforming real-world photos into Monet-inspired artworks using
**CycleGAN**, and later improving the approach with a custom **Styled
CycleGAN**.

The dataset includes:

* **Monet paintings:** 300 images
* **Photos:** 7,038 images  

All images are 256×256 RGB, stored as TFRecords.

The challenge lies in preserving content while transferring style—a delicate
balance between realism and artistry.

## Approach

The workflow began with **CycleGAN**, an architecture designed for unpaired
image-to-image translation. It uses two generators and two discriminators to
ensure that style transfer happens without losing the original content. Think
of it like translating English to French and back to English—the round trip
should preserve meaning.

Key steps:

* **Data Analysis:** Pixel intensity distributions, structural similarity
metrics, and visualizations.
* **CycleGAN Implementation:** Built with TensorFlow and Keras using UNet-based
generators and PatchGAN discriminators.
* **Loss Functions:** Adversarial, cycle-consistency, and identity losses.
* **Styled CycleGAN:** Introduced **style loss** and **content loss** using
VGG19 for perceptual features, improving artistic fidelity.
* **Hyperparameter Tuning:** Experimented with dropout rates and epochs to
balance clarity and style.

## Key Findings

* **Plain CycleGAN struggled** to produce noticeable style changes even after
50 epochs.
* **Styled CycleGAN introduced strong Monet-like patterns early (10 epochs)**,
but required tuning to reduce distortions.
* Best configuration: **Styled CycleGAN, 50 epochs, dropout=0.5**, achieving a
MiFID score of **59.90** (better than CycleGAN’s 70.76).
* Increasing dropout to 0.7 improved clarity but reduced artistic feel;
lowering it to 0.3 worsened results.

## Reflections

Styled CycleGAN clearly outperformed the baseline, showing that perceptual
losses (style and content) are critical for artistic tasks. However:

* Balancing style transfer with content preservation remains tricky.
* GPU limitations restricted deeper experiments—reducing cycle and identity
loss weights might improve results.

Future improvements could include:

* Exploring alternative architectures (e.g., Diffusion Models).
* Reducing cycle-consistency weight for more freedom in style transfer.
* Ignoring original photos entirely, as Kaggle rules allow.

***

If you're curious about the details, the full notebook is embedded below 👇

<!-- markdownlint-disable MD033 -->
<iframe title="Monet Painting CycleGAN notebook" class="notebook-embed" src="notebook.html"></iframe>

You can also view the notebook in [a separate page](notebook.html), or check it
on [GitHub](https://github.com/Farzat07/Kaggle-Mini-Project-Monet-Painting-Dataset).
