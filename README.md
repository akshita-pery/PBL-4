# Deep Learning-Based Anomaly Detection in Industrial Control Systems

## Overview

This project implements and compares three deep learning architectures for anomaly detection in Industrial Control Systems (ICS) using the Secure Water Treatment (SWaT) dataset. The objective is to detect cyber-physical attacks and abnormal operational behavior from multivariate time-series sensor data.

The following models are implemented:

- **LSTM Autoencoder** (Reconstruction-based)
- **LSTM Autoregressive Model** (Prediction-based)
- **CNN Autoencoder** (Convolution-based Reconstruction)

---

## Dataset

**Dataset:** Secure Water Treatment (SWaT)

- 11 days of continuous operation  
- 1-second sampling rate  
- 51 sensor and actuator features  
- First 7 days: Normal operation (used for training)  
- Last 4 days: 41 simulated cyber-attack scenarios  
- Binary labels: Normal / Attack  

The dataset represents a scaled-down industrial water treatment plant, including pumps, valves, flow transmitters, pressure indicators, and analyzer sensors.

---

## Project Pipeline

### 1. Data Preprocessing
- Missing value handling  
- Feature normalization  
- Sliding window generation (window size = 20)  

### 2. Model Training
- Training performed only on normal operational data  
- Loss function: Mean Squared Error (MSE)  
- Optimizer: Adam  
- Batch size: 128  
- Epochs: 12–15  

### 3. Anomaly Detection
- Threshold selection using ROC curve analysis  
- Classification based on prediction or reconstruction error  

---

## Models Implemented

### 1. LSTM Autoencoder
- Encoder–decoder architecture using LSTM layers  
- Learns compressed representation of normal sequences  
- Anomalies detected using reconstruction error  

### 2. LSTM Autoregressive Model
- Sequential LSTM model  
- Predicts next time step based on previous observations  
- Anomalies detected using prediction error  

### 3. CNN Autoencoder
- 1D convolutional encoder–decoder architecture  
- Extracts local temporal patterns  
- Anomalies detected using reconstruction error  

---

## Evaluation Metrics

Models are evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  
- Confusion Matrix  

These metrics assess detection capability, false alarm behavior, and overall classification performance.

---

## Objective

To systematically compare forecasting-based and reconstruction-based deep learning approaches for anomaly detection in industrial control systems and analyze their trade-offs under realistic attack scenarios.
