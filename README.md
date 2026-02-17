Medical AI System – End-to-End Prototype
Overview

This repository implements an end-to-end AI system for medical imaging using the PneumoniaMNIST dataset (MedMNIST v2). The system integrates:

CNN-based pneumonia classification

Vision-language model (VLM) report generation

Content-based image retrieval (CBIR) system

The project demonstrates how multiple AI components can be combined into a clinically relevant prototype.

Dataset

Dataset used: PneumoniaMNIST (MedMNIST v2)

Binary classification: Normal vs Pneumonia

Train: ~4,700 images

Validation: ~500 images

Test: ~600 images

Image size: 28×28 grayscale

Images were resized to 224×224 and converted to 3 channels for CNN compatibility.

Task 1 – CNN Classification

Model: ResNet18

Modified final layer for binary classification

Trained for 5 epochs

Weighted cross-entropy loss

Test Performance

Accuracy: ~0.85

AUC: ~0.94

High recall for pneumonia (0.98)

Conservative behavior (higher false positives)

The classifier prioritizes sensitivity, which is clinically desirable for pneumonia detection.

See: task1_classification/task1_report.md

Task 2 – Medical Report Generation

A vision-language model (BLIP-2) was used to generate radiology-style descriptions from chest X-ray images.

Findings:

The VLM often hallucinated pathological findings.

Generated outputs were repetitive across cases.

Limited sensitivity to input variation.

Low-resolution dataset likely impacted performance.

This demonstrates real-world limitations of generic VLMs in medical imaging.

See: task2_report_generation/task2_report_generation.md

Task 3 – Content-Based Image Retrieval (CBIR)

A retrieval system was built using CNN embeddings and FAISS vector search.

Pipeline:

Extract 512-dim embeddings from trained CNN

Build FAISS L2 index

Retrieve top-k similar images

Retrieval Performance

Precision@5 ≈ 0.91

The embedding space successfully clusters similar medical cases.

See: task3_retrieval_system/task3_retrieval_system.md

How to Run

Install dependencies:

pip install -r requirements.txt


Run:

notebook_demo.ipynb


The notebook:

Trains the CNN

Evaluates classification

Generates VLM reports

Builds retrieval system

Model Weights

The trained model weights are not included due to GitHub file size limits.

To reproduce results:

Run notebook_demo.ipynb

Training takes ~5–10 minutes on GPU.
