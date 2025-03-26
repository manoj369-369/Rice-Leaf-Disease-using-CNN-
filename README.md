RICE LEAF DISEASE CLASSIFICATION USING CNN

OVERVIEW

This project classifies rice leaf diseases (Leaf Smut, Brown Spot, and Bacterial Leaf Blight) using Convolutional Neural Networks (CNNs) to assist in early disease detection and better crop management.

DATASET

120 images categorized into three classes:

Leaf Smut (40 images)

Brown Spot (40 images)

Bacterial Leaf Blight (40 images)

Preprocessing Techniques:

Image resizing and normalization

Data augmentation using OpenCV & ImageDataGenerator

MODELS USED & PERFORMANCE COMPARISON

🟢 CUSTOM CNN MODEL

Architecture:

4 Convolutional layers (ReLU, MaxPooling)

Fully connected layers with Dropout

Softmax output layer

Optimizer: Adam (LR = 0.0001)

Accuracy: 85%

Why? Trained from scratch, capable of feature extraction but struggles with generalization.

🔵 MOBILENETV2 (FEATURE EXTRACTION, FROZEN LAYERS)

Architecture:

Pretrained MobileNetV2 as a feature extractor

Fully connected layers for classification

Optimizer: SGD (LR = 0.001, Momentum = 0.9)

Accuracy: 90%

Why? Leveraging pretrained features enhanced classification performance.

🔴 MOBILENETV2 (FINE-TUNED, LAST 20 LAYERS TRAINABLE)

Architecture:

Same as Model 2 but fine-tuned last 20 layers

Optimizer: SGD (LR = 0.0005, Momentum = 0.9)

Accuracy: 93%

Why? Fine-tuning enabled better adaptation to the rice leaf dataset, boosting accuracy.

🔍 RESULTS SUMMARY

✅ Fine-tuned MobileNetV2 (93%) is the best-performing model
✅ Feature extraction MobileNetV2 (90%) is effective but lags behind fine-tuning
✅ Basic CNN (85%) has the lowest accuracy due to limited dataset and no transfer learning
