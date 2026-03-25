# ECG-Heart-Disease-Project (IMAGE)
ECG image-based heart disease classification
DATASET: Public ECG Image Dataset (Mendeley Data)
https://data.mendeley.com
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

## Project Flowchart
```mermaid
flowchart TD
    A[Start] --> B[Data Collection\nMendeley ECG Images\n928 Images, 4 Classes]
    B --> C[Image Preprocessing\nResize 224x224\nNormalize & Augment]
    C --> D[Train/Val Split\n80/20]
    D --> E[Build CNN Model\nMobileNetV2 Transfer Learning]
    E --> F[Train Model\n15-30 Epochs]
    F --> G[Evaluate Model\n65.57% Accuracy]
    G --> H{Accuracy Good?}
    H -->|No| I[Try Improvements\nEfficientNet, Weight Decay]
    I --> J[Still Limited\nSmall Dataset Problem]
    J --> K[Switch to Signal Dataset\nPTB-XL 15612 Records]
    K --> L[1D CNN + LSTM Model\nBalanced Classes]
    L --> M[Train Model\n21 Epochs]
    M --> N[85.65% Accuracy\nBetter Confusion Matrix]
    N --> O[End]
```

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

A lightweight convolutional neural network (CNN) architecture, MobileNetV2, is specifically designed for mobile and embedded vision applications. Google researchers developed it as an enhancement over the original MobileNet model. Another remarkable aspect of this model is its ability to strike a good balance between model size and accuracy, rendering it ideal for resource-constrained devices. And a deep learning model pre-trained on ImageNet. It uses depthwise separable convolutions for efficient feature extraction. The model was fine-tuned on our ECG dataset for 4-class classification.
The key innovation in MobileNetV2 is the use of inverted residual blocks 
with linear bottlenecks. Unlike traditional CNNs, it first expands the 
feature channels, applies depthwise convolution, then compresses back — 
This reduces computation while preserving accuracy.

For our ECG heart disease classification project, we used Transfer Learning 
with MobileNetV2 pre-trained on ImageNet. The final classification layers 
were replaced with custom Dense layers to classify ECG images into 4 categories:
- Normal Heart
- Myocardial Infarction  
- Abnormal Heartbeat
- History of Myocardial Infarction

The model achieved 65% validation accuracy on our dataset of 928 ECG images.

## Challenges & Improvements

During this project, I trained a MobileNetV2 CNN model on ECG images to classify 4 heart conditions. While the model achieved 65.57% validation accuracy, I continued to improve it by increasing the number of epochs from 15 to 30, adding weight decay to the optimizer, and experimenting with the EfficientNetB0 architecture.

The primary limitation was the small dataset size (928 images). Despite multiple optimization attempts, accuracy remained limited, which is expected given the constrained dataset.

## Model Comparison

| Model | Dataset | Accuracy |
|-------|---------|----------|
| Our CNN (MobileNetV2) | 928 ECG Images | 65.57% |
| Reference ViT Model | 928 ECG Images (Same) | 86% |

Both models were trained on the same dataset of 928 ECG images. Despite using identical data, the ViT (Vision Transformer) model achieved 86% accuracy compared to our CNN model's 65.57%. This clearly demonstrates that ViT's self-attention mechanism learns better features from ECG images than standard CNN convolutions. However, ViT requires 30GB+ RAM, which exceeded our free Google Colab limits — making MobileNetV2 the practical choice for our resource-constrained environment.

## Future Work
The next phase of this project uses the PTB-XL ECG Signal Dataset from PhysioNet 
with a 1D CNN + LSTM model for arrhythmia classification, achieving 85.65% accuracy.
See Project 2 below!

## References
- PTB-XL Dataset: Wagner et al. (2022), PhysioNet. https://physionet.org/content/ptb-xl/1.0.3/
- MobileNetV2: Sandler et al. (2018), Google Research
- ECG Image Dataset: Khan et al. (2021), Mendeley Data

## Project 2 — ECG Signal Classification
After limited accuracy with image classification, we upgraded to the PTB-XL signal dataset.
Check the full project here: [ECG Signal Classification](ECG-Signal-Classification/README.md)
