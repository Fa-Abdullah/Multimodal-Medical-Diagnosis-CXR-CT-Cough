# Multimodal Medical Diagnosis using CXR, CT, and Cough Sound Fusion

A deep learning project that combines Chest X-ray (CXR), CT scan images, and cough sound spectrograms using multimodal fusion techniques to classify four respiratory diseases.

---

## Overview

This project investigates multimodal learning by integrating medical imaging and audio data for respiratory disease diagnosis.

Two fusion strategies are implemented:

- Intermediate Fusion
- Early Fusion

The system classifies the following conditions:

- Healthy
- Lung Cancer
- Pneumonia
- COVID-19

The objective is to improve diagnostic performance by leveraging complementary information from multiple medical modalities.

---

## Dataset

**Dataset:** CXR-CT-Cough Dataset

- Chest X-ray images
- CT scan images
- Cough audio spectrograms

Classes:

- Healthy
- Lung Cancer
- Pneumonia
- COVID-19

Dataset size:

- 500 samples per class
- 2,000 samples for each modality

Split:

- 80% Training
- 20% Validation

---

## Model Architectures

### Intermediate Fusion

Each modality is processed by an independent CNN feature extractor.

The extracted feature vectors are concatenated before the final classifier.

```
CXR CNN
          \
CT CNN ------> Concatenate --> Dense --> Softmax
          /
Audio CNN
```

---

### Early Fusion

Each modality passes through an initial convolution block.

Feature maps are resized and fused before deeper convolution layers.

This enables interactions between modalities during feature extraction.

---

## Results

| Model | Validation Accuracy |
|--------|--------------------:|
| Intermediate Fusion | **91.75%** |
| Early Fusion | 90.00% |

### Intermediate Fusion Performance

| Class | Precision | Recall | F1-score |
|--------|----------:|-------:|---------:|
| Healthy | 0.86 | 0.83 | 0.85 |
| Lung Cancer | 0.99 | 1.00 | 1.00 |
| Pneumonia | 0.93 | 0.98 | 0.96 |
| COVID-19 | 0.88 | 0.86 | 0.87 |

---

## Explainability

The project includes multiple explainable AI techniques to interpret model predictions.

Implemented methods:

- Grad-CAM
- LIME
- Saliency Maps

These visualizations help identify which regions of medical images contribute most to the predicted diagnosis.

---

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- KaggleHub
- LIME
- tf-keras-vis

---

