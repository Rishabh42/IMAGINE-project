# IMAGINE-project

# 🌆 IMAGINE: Predicting Environmental Exposures Using Street-Level Images and City Sounds

> **AI-driven environmental analytics combining vision, audio, and atmospheric data to predict real-time urban air quality and noise levels.**

---

## 📘 Overview
The **IMAGINE Project** explores how **deep learning** and **multimodal data** (images + audio) can estimate environmental exposures such as **ultrafine particle (UFP) concentration** and **noise levels**.  
It leverages **computer vision**, **spectrogram analysis**, and **XGBoost** to build scalable, low-cost alternatives to traditional air-quality sensors.

---

## 🎯 Objectives
- Predict air pollution and noise using **street-level imagery** and **city sounds**.  
- Integrate visual, acoustic, and atmospheric features for enhanced prediction accuracy.  
- Benchmark modern vision architectures (**ConvNeXt**, **ViT**, **ResNet**, **Xception**) and fuse their embeddings via **XGBoost**.  
- Evaluate model **generalization** across unseen city sites.

---

## 🧠 Methodology

### 🖼️ Image Pipeline
- Fine-tuned state-of-the-art CNN/Transformer models:
  - `ResNet50`, `Xception`, `Vision Transformer (ViT)`, `ConvNeXt`
- Extracted embeddings → merged with weather data (temperature, wind speed).  
- Combined predictions using **XGBoost** for ensemble learning.

### 🔊 Audio Pipeline
- Converted street sounds into **mel-spectrograms**.  
- Trained CNNs and ConvNeXt models to predict **noise exposure**.  
- Integrated atmospheric data to boost accuracy.

### 🧩 Generalization Testing
- Performed **leave-one-site-out** evaluation across 7 Montreal locations.  
- Validated model robustness on unseen urban sites.

### ⚗️ Deployment Simulation
- Designed inference pipeline for edge-deployable model boxes (Raspberry Pi + camera + mic).  
- Explored real-time prediction workflow via AWS S3 + Lambda + SageMaker setup.

---

## 📊 Key Results

| Target | Model | Input Type | R² (Test) | Notes |
|:-------|:------|:------------|:-----------:|:------|
| UFP Concentration | ConvNeXt + XGBoost | Image + Atmos. Data | **0.874** | Strong visual correlation |
| Noise | ConvNeXt + XGBoost | Spectrogram + Atmos. Data | **0.772** | Stable acoustic mapping |
| UFP (Generalization) | Fine-tuned ConvNeXt | Multi-Site | **0.75** | Robust to unseen data |
| Noise (Generalization) | Fine-tuned ConvNeXt | Multi-Site | **0.59** | Moderate variance |

---
