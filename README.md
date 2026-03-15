# MRI Brain Tumor Detection Using Hybrid Quantum Classical Neural Networks
This project develops a hybrid quantum–classical model for brain tumor detection from MRI images. A Fully Connected Neural Network (FCNN) is used for feature extraction, and a Variational Quantum Classifier (VQC) is used as the final classifier to improve prediction performance. The quantum-enhanced classifier achieves 96.22% test accuracy, outperforming the classical-only baseline by over 3%.

# Overview
This project explores the potential of quantum machine learning for medical image classification. We build a two-stage pipeline:

* Classical Stage -  A fully connected neural network (FCNN) extracts compact feature representations from PCA-reduced MRI scans.
* Quantum Stage - A Variational Quantum Circuit (VQC) replaces the classical classifier head, leveraging quantum entanglement and interference for improved decision boundaries.
The hybrid model demonstrates that even on a simulated quantum backend, the VQC classifier can meaningfully improve upon a strong classical baseline.

This project demonstrates how quantum machine learning can be integrated with classical deep learning for medical image classification.

# Dataset
Dataset: Br35H Brain MRI Dataset

Dataset statistics:
| Class | Images |
| --- | --- |
| tumor | 1500 |
| no_tumor | 1500 |

Images are grayscale MRI scans

# Project Pipeline
MRI Images (64×64, grayscale)
        │
        ▼
  Normalization & Flattening (4096-d)
        │
        ▼
  Data Augmentation (Gaussian noise)
        │
        ▼
  StandardScaler → PCA (150 components, 87.9% variance)
        │
        ▼
  FCNN Feature Extractor (150 → 64 → 32 → 8)
        │
        ▼
  Adapter Layer (Linear + Tanh → scale to [-π, π])
        │
        ▼
  Variational Quantum Circuit (8 qubits, 6 layers)
        │
        ▼
  Measurement (PauliZ) → Binary Prediction


# FCNN Layer Architecture
![fcnn architecture](URL_OR_PATH)
