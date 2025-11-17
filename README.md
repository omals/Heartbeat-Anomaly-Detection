# Heartbeat-Anomaly-Detection
Multiple Channel Heartbeat Audio Anomaly Classification

This repository contains the implementation of a deep learning system for classifying heartbeat audio anomalies using multiple channels of audio, combining time-domain features, frequency-domain features, and spectrogram representations using a CNN-based multi-input architecture.
The work is based on the project submitted to the Department of Computer Science, CUSAT (2024).


🔍 Overview

Traditional cardiac diagnosis relies on manual auscultation, which is subjective and varies with clinical experience.
This project introduces a multi-channel heartbeat audio classification model that integrates:

Preprocessed heartbeat audio signals

Time-domain & frequency-domain feature extraction

Multi-channel spectrogram generation

A dual-branch CNN architecture that fuses features + spectrograms

The model classifies heartbeat audio into five categories:

Normal

Murmur

Extra Heart Sound

Artifact

Extrasystole

🧠 Method Summary

Dataset: PASCAL Heart Sound Challenge dataset

Preprocessing: segmentation, normalization, denoising

Features Extracted: MFCC, spectral centroid, RMS, rolloff, ZCR, tempo

Spectrograms: Mel-spectrogram via STFT

Model:

CNN for spectrogram input

Dense layers for extracted features

Feature fusion + classification head

Training: Adam optimizer, categorical cross-entropy

Metrics: accuracy, precision, F1-score, hamming loss

🚀 Results
Model Type	Accuracy	F1-Score	Notes
Single-channel Spectrogram CNN	83.74%	86.28%	Good but unstable
Feature-based KNN	93.76%	High per-class	Strong baseline
Multi-channel CNN (Proposed)	98.27%	98.16%	Best performance ✔

The multi-channel model significantly outperformed single-channel approaches, proving the effectiveness of combining feature vectors with spectrogram channels.
