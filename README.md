# CIFAR-10 Image Classification with CNN and ResNet18

**Author:** David Schechter  
**Project Type:** Computer Vision / Deep Learning  
**Dataset:** CIFAR-10  
**Framework:** PyTorch  

---

# Project Overview

This project builds and compares two deep learning architectures for image classification on the CIFAR-10 dataset:

• A **baseline Convolutional Neural Network (CNN)**  
• A **ResNet-18 architecture**

The goal is to explore how deeper residual architectures improve performance and training stability compared to standard CNNs.

The models were trained and evaluated using PyTorch with GPU acceleration.

---

# Dataset

**CIFAR-10**

- 60,000 images
- 10 classes
- Image size: 32×32
- 50,000 training images
- 10,000 test images

Classes:

```
airplane
automobile
bird
cat
deer
dog
frog
horse
ship
truck
```

---

# Model Architectures

## Baseline CNN

Architecture:

```
Input Image
   ↓
Conv Layer
   ↓
ReLU
   ↓
Max Pool
   ↓
Conv Layer
   ↓
ReLU
   ↓
Max Pool
   ↓
Fully Connected Layer
   ↓
Softmax
```

This model serves as a **baseline computer vision classifier**.

---

## ResNet-18

ResNet introduces **residual connections**, allowing deeper networks to train effectively.

Instead of learning:

```
H(x)
```

the network learns a residual:

```
F(x) = H(x) − x
```

which improves gradient flow during backpropagation.

Architecture overview:

```
Input Image
   ↓
Conv Layer
   ↓
Residual Block × 8
   ↓
Global Average Pooling
   ↓
Fully Connected Layer
   ↓
Softmax
```

---

# Training Setup

Framework: **PyTorch**

GPU: **NVIDIA Tesla T4**

Loss Function:

```
Cross Entropy Loss
```

Optimizer:

```
Adam
```

Training Pipeline:

```
Dataset
 → DataLoader
 → Model
 → Loss Function
 → Backpropagation
 → Optimizer Step
```

---

# Training Curves

## CNN Training Loss

![CNN Training Curve](cnn_training_curve.png)

## ResNet Training Loss

![ResNet Training Curve](resnet_training_curve.png)

---

# Confusion Matrix

## CNN Confusion Matrix

![CNN Confusion Matrix](cnn_confusion_matrix.png)

## ResNet Confusion Matrix

![ResNet Confusion Matrix](resnet_confusion_matrix.png)

---

# Example Model Predictions

![ResNet Predictions](resnet_predictions.png)

These predictions highlight both correct classifications and failure cases.

Typical mistakes occur between visually similar classes:

```
cat ↔ dog
deer ↔ horse
automobile ↔ truck
```

This is expected due to the small resolution (32×32).

---

# Results

ResNet-18 significantly improves classification performance compared to the baseline CNN.

Reasons include:

• deeper feature extraction  
• residual connections improving gradient flow  
• stronger hierarchical representations  

ResNet is able to better capture complex spatial patterns in images.

---

# Repository Structure

```
cifar10-resnet18-image-classifier
│
├── cnn_training_curve.png
├── resnet_training_curve.png
├── cnn_confusion_matrix.png
├── resnet_confusion_matrix.png
├── resnet_predictions.png
│
├── cnn_baseline_model.pth
├── resnet18_model.pth
│
├── cnn_training_losses.json
├── resnet_training_losses.json
├── resnet_per_class_accuracy.json
```

---

# Key Takeaways

• building a full deep learning training pipeline  
• training CNN and ResNet architectures  
• evaluating models with confusion matrices  
• visualizing training curves  
• analyzing classification errors  

---

# Future Improvements/Possible Extensions

• data augmentation  
• deeper ResNet variants  
• transfer learning from ImageNet  
• attention mechanisms  
• feature map visualization

---

# Author

**David Schechter**

Incoming MIT '30  
Interested in AI, Machine Learning, and Computer Vision
