# ECG Signal Classification using 1D CNN + LSTM

## Overview
After working on ECG image classification with limited accuracy (65.57%), 
We upgraded to the PTB-XL ECG signal dataset from PhysioNet, which significantly 
Improved our model performance to 85.85% accuracy.

## Dataset
- **Source:** PTB-XL, PhysioNet (https://physionet.org/content/ptb-xl/1.0.3/)
- **Total Records:** 21,799 clinical 12-lead ECGs
- **Used Records:** 15,612
- **Classes:** NORM, IMI, ASMI, LVH, LAFB

## Model Architecture
- 3 x Conv1D layers (64, 128, 256 filters)
- Batch Normalization + MaxPooling
- LSTM layer (128 units)
- Dense layers with Dropout
- SoftMax output (5 classes)

## Results
| Metric | Score |
|--------|-------|
| Training Accuracy | 95.69% |
| Test Accuracy | 85.65% |
| Test Loss | 0.5257 |
| NORM F1-Score | 0.83 |
| IMI F1-Score | 0.84 |
| ASMI F1-Score | 0.86 |
| LAFB F1-Score | 0.90 |
| LVH F1-Score | 0.85 |

## Project Journey
| Project | Dataset | Model | Accuracy |
|---------|---------|-------|----------|
| ECG Image Classification | 928 Images | MobileNetV2 CNN | 65.57% |
| ECG Signal Classification | 15,612 Signals | 1D CNN + LSTM | 85.85% |

## Improvement
By switching from an image dataset to a signal dataset and using 1D CNN + LSTM,
accuracy improved from 65.57% to 85.85% — an improvement of 20.28%!
