# Football Semantic Segmentation (FCN + VGG16)

## Overview
This project implements semantic segmentation for football images using FCN32s with a VGG16 pretrained backbone.

Each pixel in the image is classified into one of 11 classes.

---

## Model
- Backbone: VGG16 (ImageNet pretrained)
- Model: FCN32s
- Framework: PyTorch
- Loss: CrossEntropyLoss
- Optimizer: Adam

---

## Dataset

The dataset is available on Kaggle:

https://www.kaggle.com/datasets/fatemehsariri/data-set

It contains:

data-set/
├── normal_only/
└── semantic_only/

---

## Classes
There are 11 classes mapped from RGB mask colors.

---

## Training Settings
- Image size: 224x224
- Batch size: 2
- Epochs: 15
- Learning rate: 0.0001
- Device: CPU / GPU

---

## Results
Training loss decreases over epochs:

Epoch 1 → 1.8  
Epoch 5 → 0.71  
Epoch 10 → 0.64  
Epoch 15 → 0.51  

---

## Visualization
The model shows:
- Input image
- Ground truth mask
- Predicted mask

---

## Requirements
torch  
torchvision  
opencv-python  
numpy  
matplotlib  

---

## Notes
- VGG16 is frozen for faster training
- Images are normalized with ImageNet mean/std
- Model can run on CPU or GPU

---

## Author
Deep learning project for semantic segmentation practice
