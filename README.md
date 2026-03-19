# Autonomous Vehicle Road Detection & Segmentation

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Computer Vision](https://img.shields.io/badge/Computer_Vision-000000?style=for-the-badge)

## Overview
This repository contains a deep learning project focused on real-time semantic segmentation of drivable road areas for autonomous driving applications. By leveraging a custom **UNet architecture** implemented in **PyTorch**, the model accurately parses YOLO-formatted polygon annotations into binary masks and predicts road boundaries with high precision and speed.

##  Key Performance Metrics
- **Validation Dice Score:** 0.9130
- **Inference Speed:** ~115 FPS (Real-time capability)
- **Epochs Trained:** 50

##  Model Architecture
The model uses a classic **UNet** fully convolutional network architecture designed for biomedical image segmentation, adapted here for road surface detection. 
- **Encoder:** Extracts spatial features and reduces dimensions using consecutive `3x3` convolutions, BatchNorm, ReLU, and MaxPooling.
- **Decoder:** Recovers spatial dimensions using Bilinear Upsampling and concatenates feature maps (skip connections) from the encoder to retain high-resolution details.
- **Output:** A `1x1` convolution with a Sigmoid activation function to output a binary mask (Road vs. Background).

##  Dataset
The model is trained on a road segmentation dataset containing RGB images and corresponding YOLO polygon annotations (`.txt` files).

> **Note:** The dataset is not included in this repository due to size constraints. 
1. Download the dataset from Kaggle: [Insert Kaggle Dataset Link Here]
2. Extract the data and organize it into the following structure:
   ```text
   /dataset
       /train
           /images
           /labels
       /valid
           /images
           /labels
