# Lung Cancer CT Scan Classification using Deep Learning

## Overview

This project presents a deep learning-based framework for automated multi-class classification of lung CT scan images into **Benign**, **Malignant**, and **Normal** categories using the IQ-OTH/NCCD Lung Cancer Dataset.

The system explores and compares multiple deep learning architectures ranging from a custom CNN baseline to transfer learning and fine-tuned EfficientNet models in order to identify the most effective architecture for lung cancer CT scan classification.

---

## Dataset

**Dataset:** IQ-OTH/NCCD Lung Cancer Dataset
**Source:** Kaggle
**Link:** https://www.kaggle.com/datasets/adityamahimkar/iqothnccd-lung-cancer-dataset

### Dataset Classes

* Benign
* Malignant
* Normal

---

## Pretrained Model Weights

Download the trained model weights here:

**Fine-Tuned EfficientNetB7 (.keras):**
https://www.kaggle.com/datasets/raghavgupta211/lung-cancer-classification-model-weights

---

## Project Objectives

* Build an automated lung CT scan classification pipeline
* Compare baseline CNN performance against transfer learning architectures
* Evaluate the impact of fine-tuning pretrained models
* Analyze model performance using multiple evaluation metrics

---

## Methodology

### Data Preprocessing

* Loaded CT scan images from class-specific directories
* Resized images for model compatibility
* Converted grayscale scans to RGB for transfer learning models
* Applied EfficientNet-specific preprocessing
* Performed train/validation split for model development

### Data Augmentation

Applied augmentation during training to improve generalization:

* Rotation
* Horizontal and Vertical Flips
* Translation
* Zoom
* Brightness Adjustment

---

## Models Implemented

### 1. Custom CNN

Baseline convolutional neural network developed from scratch for benchmark comparison.

### 2. EfficientNetB0

Transfer learning model using pretrained EfficientNetB0 as frozen feature extractor.

### 3. Fine-Tuned EfficientNetB7

Transfer learning model with partially unfrozen EfficientNetB7 backbone for domain-specific fine-tuning.

---

## Training Strategy

* **Loss Function:** Categorical Crossentropy
* **Optimizer:** Adam
* **Callbacks Used:**

  * ModelCheckpoint
  * EarlyStopping
  * ReduceLROnPlateau

---

## Results

| Model                     | Accuracy   | Precision  | Recall     | F1 Score   |
| ------------------------- | ---------- | ---------- | ---------- | ---------- |
| Custom CNN                | 97.73%     | 97.81%     | 97.73%     | 97.68%     |
| EfficientNetB0            | 93.18%     | 92.92%     | 93.18%     | 92.99%     |
| Fine-Tuned EfficientNetB7 | **98.18%** | **98.18%** | **98.18%** | **98.18%** |

---

## Performance Analysis

* **Fine-Tuned EfficientNetB7** achieved the best overall performance across all evaluation metrics.
* **Custom CNN** delivered highly competitive performance despite significantly lower complexity.
* Fine-tuning substantially improved performance over frozen transfer learning.

---

## Evaluation Metrics

Models were assessed using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* ROC-AUC Curves

---

## Key Insights

* Transfer learning with fine-tuning significantly improves classification performance.
* Lightweight custom CNNs can remain competitive on specialized medical datasets.
* Fine-tuning pretrained backbones enables stronger domain adaptation for CT scan analysis.

---

## Future Improvements

* Implement patient-wise train/test splitting to reduce data leakage risk
* Add Grad-CAM / Explainability Visualizations
* Perform Hyperparameter Optimization
* Validate on External Lung CT Datasets
* Deploy as Clinical Decision Support Prototype

---

## Tech Stack

* Python
* TensorFlow / Keras
* OpenCV
* NumPy / Pandas
* Matplotlib / Seaborn
* Scikit-learn

---

## Disclaimer

This project is intended for **research and educational purposes only** and is **not a clinical diagnostic tool**.

---

## Author

**Raghav Gupta**
