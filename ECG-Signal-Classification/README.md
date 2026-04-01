# ECG Signal Classification using 1D CNN + LSTM

## 📌 Overview
After working on ECG image classification with limited accuracy (65.57%), the project was extended to ECG signal classification using the PTB-XL dataset from PhysioNet. This significantly improved the model performance, achieving a peak accuracy of 85.65% with a final test accuracy of 84.93%

Based on feedback from the project guide, the model was further improved by balancing the dataset (690 samples per class) and fine-tuning the architecture, resulting in better classification performance and improved confusion matrix results.

## 📊 Dataset
- **Source:** PTB-XL Dataset (PhysioNet)  
  https://physionet.org/content/ptb-xl/1.0.3/
- **Total Records:** 21,799 clinical 12-lead ECG signals  
- **Used Records:** 15,612  
- **Classes:** NORM, IMI, ASMI, LVH, LAFB

## 🧠 Model Architecture
- **4 × Conv1D layers** with 64, 128, 256, and 128 filters  
- **Batch Normalization** and **MaxPooling1D** after each convolution block  
- **2 × LSTM layers** with 256 and 128 units  
- **Dense layers** with 256 and 128 neurons, followed by Dropout  
- **Softmax output layer** for 5-class classification

## 🔄 Workflow
1. Data Loading  
2. Signal Preprocessing  
3. Dataset Balancing  
4. Train-Test Split  
5. Model Building (1D CNN + LSTM)  
6. Model Training  
7. Model Evaluation
8. Confusion Matrix and F1-score Analysis
9. ROC-AUC Curve Evaluation
10. Performance Comparison
  
## 📈 Results

| Metric | Score |
|--------|-------|
| Training Accuracy | 95.69% |
| Test Accuracy | 84.93% |
| Test Loss | 0.5257 |
| NORM F1-Score | 0.83 |
| IMI F1-Score | 0.84 |
| ASMI F1-Score | 0.86 |
| LAFB F1-Score | 0.90 |
| LVH F1-Score | 0.85 |

Additional evaluation metrics such as **Confusion Matrix**, **Classification Report (Precision, Recall, F1-score)**, and **ROC-AUC curves** have been included in the updated notebook for comprehensive performance analysis.

The model demonstrates strong performance across all five classes, with the highest F1-score observed for LAFB (0.90).

## 🚀 Project Journey

| Project | Dataset | Model | Accuracy |
|---------|---------|-------|----------|
| ECG Image Classification | 928 Images | MobileNetV2 CNN | 65.57% |
| ECG Signal Classification | 3,450 balanced signals
(from 15,612 records) | 1D CNN + LSTM | 85.65% |

## 📈 Improvement
By transitioning from ECG image-based classification to ECG signal-based classification and applying a 1D CNN + LSTM architecture, the model accuracy improved from **65.57%** to **85.65%**, resulting in an overall improvement of **20.08%**.

## 🔮 Future Scope

* Perform hyperparameter tuning for improved generalization
* Extend classification to additional ECG conditions and arrhythmias
* Apply cross-validation and external dataset validation
* Deploy as a healthcare diagnostic decision support tool
* Explore transformer-based architectures for ECG sequence modeling

Signal-based ECG classification performed significantly better
than image-based classification.
