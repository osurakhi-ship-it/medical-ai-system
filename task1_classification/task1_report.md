Task 1 – Pneumonia Classification
Objective

Build a CNN-based system for pneumonia detection using the PneumoniaMNIST dataset.

Model Architecture

Base model: ResNet18

Final fully connected layer modified for 2 classes

Input: 224×224 RGB (converted from grayscale)

Training Setup

Optimizer: Adam

Loss: Weighted Cross-Entropy

Epochs: 5

Batch size: 64

Results (Test Set)

Accuracy: ~0.85

AUC: ~0.94

Precision (Pneumonia): 0.82

Recall (Pneumonia): 0.98

The model shows very high recall for pneumonia, indicating strong sensitivity.

Error Analysis

False positives were higher for normal cases.

Model behavior is conservative (prefers predicting pneumonia).

This is clinically acceptable for screening systems.

Conclusion

The CNN provides strong pneumonia detection performance and forms the foundation for subsequent tasks.
