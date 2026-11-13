# Melanoma Detection with a Custom CNN

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Individual assignment · **Year:** 2022

## Problem
Melanoma accounts for most skin-cancer deaths, and early detection is critical. The task was to build a CNN that classifies dermoscopic images from the ISIC dataset into 9 skin-lesion classes, to help dermatologists triage cases.

## Approach
- Built a CNN from scratch in TensorFlow/Keras with in-model rescaling, and `cache()`/`prefetch()` input pipelines.
- **Model 1 (baseline):** clear overfitting, with training accuracy at 91% but validation accuracy at only 52%.
- **Model 2:** added data augmentation and dropout, which removed overfitting but left the model underfitting (validation accuracy about 56%).
- **Model 3:** analysed the class imbalance, then rebalanced the classes using Augmentor (500 extra samples per class) and retrained.

## Results
- Validation accuracy rose from **52% to 79%** after class rebalancing, with training accuracy at 94%.
- Shows the iterative diagnosis of overfitting and underfitting, and the effect of class imbalance on medical image models.

## Tools
Python, TensorFlow/Keras, Augmentor, NumPy, Matplotlib, Google Colab (GPU)

## Files
- [`melanoma_detection_cnn.ipynb`](melanoma_detection_cnn.ipynb)

Originally published at [pankhurimishra81/MelanomaDetectionAssignment](https://github.com/pankhurimishra81/MelanomaDetectionAssignment).
