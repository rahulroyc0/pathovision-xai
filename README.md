# Interpretable Medical Image Classification with CNNs and XAI

This project investigates **accurate and interpretable histopathological image classification** using deep learning models on the **PathMNIST** dataset. We evaluate models of increasing complexity and apply **Explainable AI (XAI)** techniques to provide visual explanations suitable for medical imaging applications.

This work was developed as part of **ECE1513 – Introduction to Machine Learning** at the **University of Toronto**.

---

## 📌 Dataset

* **PathMNIST** (MedMNIST v2)
* 9-class histopathological tissue classification
* Original resolution: 28×28 (upsampled to 64×64)
* Balanced class distribution

<p align="center">
  <img src="Figure\pathmnist_9_classes.png" width="600"/>
</p>

---

## 🧠 Models Evaluated

We follow a structured modeling progression:

* **Fully Connected Network (FNN)**

  * Baseline model without spatial inductive bias
  * Accuracy: **~67%**

* **SimpleCNN**

  * Convolution + pooling blocks for spatial feature extraction
  * Accuracy: **~95%**

* **Pretrained ResNet-18 (ImageNet)**

  * Transfer learning with residual connections
  * Accuracy: **~98%** (best performance)

<p align="center">
  <img src="Figure\accuracy_comparison.png" width="600"/>
</p>

---

## 🔍 Explainable AI (XAI)

To ensure interpretability in clinical contexts, we apply:

* **Grad-CAM**
* **Grad-CAM++**

These methods highlight the image regions most influential to each prediction, allowing visual inspection of model reasoning.

<p align="center">
  <img src="xai_outputs_resnet\example_0.png" width="600"/>
</p>

---

## 📊 Results Summary

| Model                  | Accuracy |
| ---------------------- | -------- |
| FNN                    | ~67%     |
| SimpleCNN              | ~95%     |
| ResNet-18 (Pretrained) | ~98%     |

* Deeper convolutional architectures significantly outperform shallow models.
* Grad-CAM and Grad-CAM++ consistently highlight meaningful morphological regions.
* Grad-CAM++ provides slightly finer localization in some cases.

---

## ⚙️ Training Details

* Framework: **PyTorch**
* Optimizer: **Adam**
* Learning rate:

  * FNN / SimpleCNN: 1e-3
  * ResNet-18 fine-tuning: 1e-4
* Loss: Cross-Entropy
* Regularization: Dropout (0.3–0.5)

---

## 📁 Repository Structure

```
.
├── PathMNIST-XAI-Classification/
│   └── PathMNIST-XAI-Classification.ipynb
├── Figure/
│   ├── accuracy_comparison.png.png
│   ├── pathminst_9_classes.png
├── xai_outputs_cnn/
├── xai_outputs_resnet/
└── README.md
```

---

## 📄 Report

For full experimental details, architectural explanations, and additional visualizations, see:

**`report.pdf`**

---

## 🎯 Key Takeaways

* Transfer learning significantly improves medical image classification accuracy.
* CNN-based models combined with XAI offer both **performance and transparency**.
* Interpretability is essential for trustworthy deployment in medical imaging.

---

## 📚 References

* MedMNIST v2 Dataset
* Grad-CAM / Grad-CAM++
* ResNet-18 (He et al.)

---

