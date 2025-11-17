# Heartbeat-Anomaly-Detection  
**Multiple Channel Heartbeat Audio Anomaly Classification**

This repository contains the implementation of a deep learning system for classifying heartbeat audio anomalies using multiple audio channels. The model integrates **time-domain features**, **frequency-domain features**, and **spectrogram representations** using a **CNN-based multi-input architecture**.  
This work is based on the project submitted to the **Department of Computer Science, CUSAT (2024)**.

---

## Overview

Traditional cardiac diagnosis relies heavily on manual auscultation, which can be subjective and inconsistent.  
This project proposes a **multi-channel heartbeat anomaly classification system** that combines:

- Preprocessed heartbeat audio signals  
- Time-domain & frequency-domain feature extraction  
- Multi-channel spectrogram generation  
- A dual-branch CNN architecture (features + spectrograms)  

### The model classifies heartbeat audio into five categories:

- **Normal**
- **Murmur**
- **Extra Heart Sound**
- **Artifact**
- **Extrasystole**

---

## Method Summary

**Dataset:** PASCAL Heart Sound Challenge  
**Preprocessing:**  
- Audio segmentation  
- Normalization  
- Noise reduction  

**Feature Extraction:**  
- MFCC  
- Spectral Centroid  
- RMS Energy  
- Spectral Rolloff  
- Zero Crossing Rate (ZCR)  
- Tempo  

**Spectrograms:**  
- Mel-Spectrograms generated using STFT  

**Model Architecture:**  
- CNN branch for spectrogram input  
- Dense branch for numerical feature input  
- Feature fusion + fully connected classifier  

**Training:**  
- Optimizer: Adam  
- Loss: Categorical Cross-Entropy  
- Metrics: Accuracy, Precision, Recall, F1-score, Hamming Loss  

---

## Results

| Model Type                     | Accuracy | F1-Score | Notes               |
|-------------------------------|----------|----------|---------------------|
| Spectrogram CNN (Single-Channel) | 83.74%   | 86.28%   | Good but unstable   |
| Feature-based KNN             | 93.76%   | High per-class | Strong baseline |
| **Multi-Channel CNN (Proposed)** | **98.27%** | **98.16%** | **Best performance ✔** |

The multi-channel model significantly outperformed both spectrogram-only and feature-only models, demonstrating the power of **feature–spectrogram fusion** for medical audio analysis.
