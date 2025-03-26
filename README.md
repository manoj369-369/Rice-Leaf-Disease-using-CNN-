Rice Leaf Disease Classification using CNN
This project classifies rice leaf diseases (Leaf Smut, Brown Spot, Bacterial Leaf Blight) using Convolutional Neural Networks (CNNs) to help farmers detect diseases early.

Dataset
120 images (40 per class)

Preprocessing: Image resizing, normalization, and augmentation

Models Used & Accuracy
Custom CNN → 85% (Basic model, lacks generalization)

MobileNetV2 (Feature Extraction) → 90% (Uses pretrained features, better performance)

MobileNetV2 (Fine-Tuned, Last 20 Layers Trainable) → 93% (Best performance, adapts well to the dataset)

Why These Results?
✅ Fine-tuned MobileNetV2 works best due to transfer learning.
✅ Feature extraction alone helps but isn’t as good as fine-tuning.
✅ Basic CNN struggles with feature learning due to dataset size.
