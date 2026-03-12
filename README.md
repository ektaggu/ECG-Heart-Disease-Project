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
