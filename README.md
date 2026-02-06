# 🇨🇦 Multi-Task Learning: CIFAR-10 Classification & AQI Regression
**Architecture:** MobileNetV2 Backbone with Dual-Head Output  
**Dataset:** Canadian CIFAR-10 (Canadian Institute for Advanced Research)

---

## 📌 Project Overview
This repository features a **Multi-Task Learning (MTL)** system developed in Python using TensorFlow and Keras. Most standard models focus on a single objective; however, this project utilizes a shared feature extractor (MobileNetV2) to solve two distinct problems simultaneously:

1. **Image Classification:** Categorizing images into one of the 10 standard CIFAR-10 classes.
2. **AQI Regression:** Predicting a synthetic Air Quality Index (AQI) value based on the visual features of the image.



---

## 🏗️ Technical Architecture
The model leverages **Transfer Learning** via a pre-trained **MobileNetV2** backbone. By freezing the early layers, the model utilizes high-level feature maps which are then branched into two specialized heads:

* **Shared Layers:** MobileNetV2 (ImageNet weights) + Global Average Pooling.
* **Classification Head:** Dense (128) -> Dropout -> Softmax (10 outputs).
* **Regression Head:** Dense (128) -> Dense (1 output, Linear activation).

---

## 📊 Performance Metrics
The model was trained for 10 epochs on a T4 GPU. The results demonstrate the efficiency of shared feature learning:

| Task | Metric | Value |
| :--- | :--- | :--- |
| **Classification** | Accuracy | **~80.37%** |
| **Regression** | Mean Absolute Error (MAE) | **~1.77** |



---

## 💾 Download Model Weights
Because the model was saved with full optimizer states and gradients for reproducibility, the final `.h5` file is **649 MB**. This exceeds GitHub's standard upload limit.

**Download the `ccp_final_model.h5` here:** 👉 https://drive.google.com/file/d/138wPjTNeCoysYeO001exgllSE9yBUpU-/view?usp=sharing

---

## 🚀 How to Run
1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/CIFAR10-MultiTask.git](https://github.com/YOUR_USERNAME/CIFAR10-MultiTask.git)
