# ECG-Heart-Disease-Project
ECG image-based heart disease classification Dataset:
PRIMARY DATASET- Public ECG Image Dataset (Mendeley Data)
https://data.mendeley.com
SECONDARY DATASET- Reference: Khan, A.H., Hussain, M., Malik, M.K. (2021)
ECG Images Dataset of Cardiac and COVID-19 Patients
NIH-supported PhysioNet Dataset
PTB-XL: A Large Public ECG Dataset
Source: https://physionet.org/content/ptb-xl/1.0.3/
Used for validation and comparison

## Overview
This project classifies ECG images into 4 heart conditions using Deep Learning (CNN - MobileNetV2).

## Heart Conditions Detected
- Normal Heart
- Myocardial Infarction
- Abnormal Heartbeat
- History of Myocardial Infarction

## Dataset
- Total Images: 928
- Training: 745 images
- Validation: 183 images
- Classes: 4

## Model
- Architecture: MobileNetV2 (Transfer Learning)
- Framework: TensorFlow/Keras
- Accuracy: 65%

## Results
![Training Graphs](training_graphs.png)
![Confusion Matrix](confusion_matrix.png)

## Steps
1. Data Collection
2. Image Preprocessing
3. Train/Val Split (80/20)
4. Build CNN Model
5. Train Model
6. Evaluate Model
7. Prediction

## An Overview of Electrocardiogram (ECG or EKG)
<img src="downloadECG%20EKG%20DIAGRAM.jpg" width="600"/>

An electrocardiogram records the electrical signals in the heart. It is a common, painless test used to detect heart problems and quickly monitor the heart's health.

It is used to determine or detect:
- Irregular heart rhythms (arrhythmias)
- Blocked or narrowed arteries causing chest pain or a heart attack
- Whether you have had a previous heart attack
- How well certain heart disease treatments are working

## Identifying Heart Disease from ECG Images with Deep Learning

This project uses a dataset of annotated ECG images and their corresponding heart disease labels to train a CNN (MobileNetV2) model to identify different heart conditions based on the input ECG image.

## Data Preprocessing

The original images were resized to 224x224 to make deep learning processing efficient. Images were normalized and augmented using rotation, zoom, and horizontal flip to improve model performance.

## CNN Architecture (MobileNetV2)
<img src="mobilenet.png" width="600"/>

MobileNetV2 is a lightweight deep learning model pre-trained on ImageNet. It uses depthwise separable convolutions for efficient feature extraction. The model was fine-tuned on our ECG dataset for 4-class classification.
