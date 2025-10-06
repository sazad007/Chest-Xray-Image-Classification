# 🩺 Chest X-Ray Image Classification for Pneumonia Detection

## 🧠 Overview
This project explores deep learning models for the automatic classification of chest X-ray images into **Pneumonia** and **Normal** categories.  
Two different convolutional neural network (CNN) approaches were implemented and compared:
1. 🧩 **Pure CNN** – a custom-built convolutional model trained from scratch.  
2. ⚙️ **MobileNet** – a transfer learning model using pre-trained weights.

The models were trained and evaluated on the **Chest X-Ray Pneumonia** dataset from Kaggle, which contains pediatric chest X-rays labeled as *Normal* or *Pneumonia*.

---

## 📂 Dataset
**Source:** [Chest X-Ray Images (Pneumonia) – Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia/versions/2)

| Subset | Normal | Pneumonia |
|:-------|--------:|----------:|
| Train  | 1341 | 3875 |
| Val   | 234  | 390  |
| Test    | 8    | 8    |

All images are grayscale radiographs of the chest area and were resized and normalized before model input.

---

## 🔧 Methodology

### 🧩 1. Pure CNN Model
A simple CNN architecture was implemented with multiple convolutional, pooling, and dense layers followed by dropout regularization.

**Results:**
- 🏆 **Best Validation Accuracy:** 90.38% (Epoch 6)  
- 🧾 **Test Images Labeled Correctly:** 13 / 16  

The model demonstrated strong performance with a relatively shallow architecture, highlighting the effectiveness of CNNs in medical image classification tasks.

---

### ⚙️ 2. MobileNet (Transfer Learning)
MobileNet, a lightweight CNN pre-trained on ImageNet, was fine-tuned on the same dataset.  
Transfer learning helped the model converge faster and generalize better despite the limited dataset size.

**Results:**
- 🏆 **Best Validation Accuracy:** 87.50% (Epoch 23)  
- 🧾 **Test Images Labeled Correctly:** 15 / 16  

Although the validation accuracy was slightly lower than the pure CNN model, the transfer-learned MobileNet performed better in test generalization.

---

## 📊 Evaluation Summary

| Model | Validation Accuracy | Test Accuracy (sample) | Correct Predictions |
|:------|:-------------------:|:----------------------:|:-------------------:|
| 🧩 Pure CNN | 90.38% | — | 13 / 16 |
| ⚙️ MobileNet | 87.50% | — | 15 / 16 |

Both models successfully distinguished between pneumonia and normal cases, demonstrating high reliability for real-world diagnostic assistance.

---

## 🔍 Key Observations
- 🧩 **Pure CNN** achieved slightly higher validation accuracy but showed signs of mild overfitting.  
- ⚙️ **MobileNet** exhibited better **generalization**, indicating the power of transfer learning even with smaller datasets.
- The number of normal chest xray images were less than pneumonia affected images which resulted in high number of wrong prediction of NORMAL chest xrays.   
- Further improvements could be achieved using:
  - Advanced data augmentation  
  - Dropout and regularization tuning  
  - Fine-tuning deeper pre-trained layers

---

## 🧾 Conclusion
This study confirms that convolutional neural networks, both from-scratch and pre-trained, can effectively classify pneumonia from chest X-ray images.  
While both approaches yielded strong results, transfer learning offered a balance between training efficiency and predictive stability, making it more suitable for deployment in limited-data medical scenarios.

---

## 📚 Citation
Dataset:
> Paul Mooney. *Chest X-Ray Images (Pneumonia)*. Kaggle.  
> https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia
