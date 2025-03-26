# 🌾 RICE LEAF DISEASE CLASSIFICATION USING CNN 🌾

## 🏆 OVERVIEW  
🚀 This project **classifies rice leaf diseases** (**Leaf Smut, Brown Spot, and Bacterial Leaf Blight**) using **Convolutional Neural Networks (CNNs)**.  
🌱 Early disease detection helps **farmers improve crop management & yield**.

---

## 📂 DATASET  
📸 **120 images** across three disease classes:  
✅ **Leaf Smut** - 40 images  
✅ **Brown Spot** - 40 images  
✅ **Bacterial Leaf Blight** - 40 images  

📌 **Preprocessing Techniques**:  
🔹 **Image Resizing & Normalization** - Standardizes input size.  
🔹 **Data Augmentation** - Enhances variability using **OpenCV & ImageDataGenerator**.

---

## ⚡ MODELS USED & PERFORMANCE COMPARISON  

### 🟢 **1️⃣ CUSTOM CNN MODEL**  
🛠 **Architecture**:  
✔️ 4 **Convolutional Layers** (ReLU, MaxPooling)  
✔️ **Dropout** for regularization  
✔️ **Softmax Output Layer**  

🔹 **Optimizer**: Adam (**LR = 0.0001**)  
🎯 **Accuracy**: **85%**  

📌 **Insight**: Trained from scratch, capable of feature extraction but **struggles with generalization**.  

---

### 🔵 **2️⃣ MOBILENETV2 (FEATURE EXTRACTION, FROZEN LAYERS)**  
🛠 **Architecture**:  
✔️ **Pretrained MobileNetV2** as a feature extractor  
✔️ Fully connected layers for classification  

🔹 **Optimizer**: SGD (**LR = 0.001, Momentum = 0.9**)  
🎯 **Accuracy**: **90%**  

📌 **Insight**: Leveraging **pretrained features** improved classification but lacks dataset-specific adaptation.  

---

### 🔴 **3️⃣ MOBILENETV2 (FINE-TUNED, LAST 20 LAYERS TRAINABLE)**  
🛠 **Architecture**:  
✔️ **Same as Model 2**, but **fine-tuned last 20 layers**  

🔹 **Optimizer**: SGD (**LR = 0.0005, Momentum = 0.9**)  
🎯 **Accuracy**: **93%**  

📌 **Insight**: Fine-tuning **improved adaptation**, boosting accuracy significantly.  

---

## 📊 PERFORMANCE COMPARISON  
| Model | Optimizer | Learning Rate | Accuracy |
|--------|-----------|--------------|-----------|
| 🟢 **Custom CNN** | Adam | 0.0001 | **85%** |
| 🔵 **MobileNetV2 (Frozen Layers)** | SGD | 0.001 | **90%** |
| 🔴 **MobileNetV2 (Fine-Tuned)** | SGD | 0.0005 | **93%** |

📌 **Key Takeaways**:  
✅ **Fine-tuned MobileNetV2 (93%)** is the best-performing model.  
✅ **Feature Extraction MobileNetV2 (90%)** is effective but lags behind fine-tuning.  
✅ **Basic CNN (85%)** has the lowest accuracy due to limited dataset & lack of transfer learning.

---

## 🛠 INSTALLATION  
📥 **Install dependencies**:  
```bash
pip install tensorflow keras numpy matplotlib scikit-learn opencv-python
