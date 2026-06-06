# Football Semantic Segmentation Report

---

## 1. Introduction

Semantic segmentation is a computer vision task where each pixel in an image is assigned a class label. Unlike image classification, which predicts a single label for the entire image, segmentation provides a detailed pixel-level understanding.

In this project, we focus on semantic segmentation of football images, where the goal is to classify each pixel into meaningful categories such as players, background, and field regions.

---

## 2. Objective

The main objectives of this project are:

- To implement a deep learning model for semantic segmentation
- To classify each pixel in football images into predefined classes
- To evaluate model performance using visual results
- To build a baseline model that can be improved in future work

---

## 3. Dataset

The dataset was provided by the course instructor and is not publicly available.

It consists of two main folders:

data-set/

├── normal_only/ 


└── semantic_only/    

Each image has a matching mask with RGB color-coded labels representing different classes.

---

## 4. Data Preprocessing

Before feeding the data into the model, several preprocessing steps are applied:

- Images are resized to 224x224
- Images are normalized using ImageNet statistics
- Masks are converted from RGB colors to class indices
- Data is loaded using a custom PyTorch Dataset class

---

## 5. Model Architecture

The model used in this project is FCN32s with a VGG16 backbone.

### Backbone
A pretrained VGG16 model is used to extract high-level features from input images.

### Segmentation Head
The extracted features are passed through fully convolutional layers to predict pixel-wise class scores.

### Upsampling
A transposed convolution layer is used to restore the output to the original image resolution.

---

## 6. Training Setup

The model is trained using the following configuration:

- Input size: 224 × 224
- Batch size: 2
- Epochs: 15
- Learning rate: 0.0001
- Optimizer: Adam
- Loss function: CrossEntropyLoss
- Device: CPU / GPU (depending on availability)

---

## 7. Training Process

During training, the model learns to minimize the difference between predicted segmentation maps and ground truth masks.

The loss gradually decreases over epochs, indicating that the model is learning meaningful representations.

Example training progress:

Epoch 1  → Loss: 1.84  
Epoch 5  → Loss: 0.86  
Epoch 10 → Loss: 0.64  
Epoch 15 → Loss: 0.51  

---

## 8. Evaluation

The model is evaluated using visual inspection rather than numerical metrics.

For each sample, we display:

- Input Image
- Ground Truth Mask
- Predicted Mask

This helps in understanding how well the model performs on unseen data.

---

## 9. Results

The model achieves reasonable segmentation performance on simple images. However, performance decreases on more complex scenes with:

- Occlusions between players
- Low lighting conditions
- Dense objects in the scene

---

## 10. Challenges

Several challenges were observed during this project:

- Small batch size due to CPU limitations
- Limited dataset diversity
- Difficulty in segmenting overlapping objects
- Sensitivity to lighting conditions

---

## 11. Future Improvements

To improve performance, the following enhancements can be applied:

- Replace FCN with UNet or DeepLabV3
- Add data augmentation techniques
- Increase training epochs
- Use a larger dataset
- Fine-tune VGG backbone instead of freezing it

---

## 12. Conclusion

This project demonstrates a baseline approach to semantic segmentation using FCN with a VGG16 backbone. While the model produces reasonable results, there is significant room for improvement using more advanced architectures and training strategies.

---

## 13. Author

This project was developed for educational purposes in deep learning and computer vision.
