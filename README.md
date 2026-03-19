<img width="993" height="339" alt="__results___0_1" src="https://github.com/user-attachments/assets/1dd34f36-febd-4621-96a8-08a3d4826f89" /># Autonomous Vehicle Road Detection & Segmentation

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
3. Update the directory paths in the main execution block of the code.

## Installation & Requirements

To run this project, you need Python 3.8+ and the following libraries:
pip install torch torchvision Pillow numpy matplotlib

## Visual Results
Below are sample predictions from the validation set showing the original image, the predicted binary mask, and the overlay.

<img width="993" height="339" alt="__results___0_5" src="https://github.com/user-attachments/assets/aef7a789-190c-4900-bbeb-c292edeece90" />
<img width="993" height="339" alt="__results___0_6" src="https://github.com/user-attachments/assets/3203fa24-1062-4fe8-b2d4-aa063c1e8610" />
<img width="993" height="339" alt="__results___0_7" src="https://github.com/user-attachments/assets/86abacb9-3468-49b0-a512-a97595c178e9" />
<img width="993" height="339" alt="__results___0_8" src="https://github.com/user-attachments/assets/7ac56682-4d3a-4553-a620-58146151b516" />
<img width="993" height="339" alt="__results___0_2" src="https://github.com/user-attachments/assets/4bb9806b-952e-4d8c-ad74-31e93aa00298" />
<img width="993" height="339" alt="__results___0_3" src="https://github.com/user-attachments/assets/ae88828a-05d2-4737-99d7-d31891c3cc03" />
<img width="993" height="339" alt="__results___0_4" src="https://github.com/user-attachments/assets/564ec4a3-3eea-46e6-932d-4036c6f51b2f" />


##How to Run
Ensure your dataset is correctly linked.

Run the training script or Jupyter Notebook:

python road_segmentation.py
# or open road-detection-segmentation-pytorch-unet-model.ipynb
