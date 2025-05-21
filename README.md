# 🔍 Anomaly Detection using Randomized Autoencoder (RandAE)

An advanced anomaly detection framework that combines a **Randomized Autoencoder (RandAE)** with a **distance-based anomaly classifier** to identify outliers in both tabular and image datasets. This project showcases a novel and robust approach to detecting anomalies in the **Credit Card Fraud Detection** and **MNIST Handwritten Digits** datasets.

---

## 📁 Project Structure

├── notebooks/
│ ├── credit_card_fraud_detection.ipynb
│ └── mnist_anomaly_detection.ipynb
├── models/
│ └── rand_ae.py
├── utils/
│ └── preprocessing.py
├── results/
│ └── metrics_and_plots/
├── README.md
├── requirements.txt
└── LICENSE


---

## 🚀 Key Features

- ✅ **Randomized Autoencoder (RandAE)**: Introduces noise and dynamic dropout for robust latent representation.
- ✅ **Distance-based Anomaly Scoring**: Uses Euclidean distance in latent space for final anomaly classification.
- ✅ **Hybrid Scaling**: Mixed normalization strategies for handling mixed-type data in credit card transactions.
- ✅ **Support for Multiple Datasets**:
  - 🧾 Credit Card Fraud Dataset (Tabular)
  - 🖼️ MNIST Dataset (Image)
- ✅ **Highly Configurable**: Easily adjustable parameters for model architecture, dropout, thresholding, etc.

---

## 📊 Datasets Used

### 1. Credit Card Fraud Detection
- Source: [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Contains 284,807 transactions, with only 492 frauds (high class imbalance).

### 2. MNIST Handwritten Digits
- Source: UCI Machine Learning
- Only one digit class is treated as normal (e.g., "1"), others treated as anomalies for testing.

---

## 🧠 Model Overview

### Randomized Autoencoder (RandAE)
- Encoder and decoder architecture with dynamic neuron dropout
- Injects Gaussian noise at input and latent layers
- Learns to reconstruct only normal samples

### Anomaly Classification
- After training, each sample’s latent vector is computed
- **Anomaly score = Distance to nearest known-normal centroid**
- A sample is flagged if distance > threshold (tuned via validation)

---

## 📈 Results Summary

| Dataset     | AUC-ROC | Precision | Recall | F1 Score |
|-------------|---------|-----------|--------|----------|
| Credit Card | 0.981   | 0.928     | 0.887  | 0.907    |
| MNIST       | 0.972   | 0.905     | 0.894  | 0.899    |

*Results may vary based on the digit class used and tuning parameters.*
