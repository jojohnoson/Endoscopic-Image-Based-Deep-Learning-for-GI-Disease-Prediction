# Endoscopic Image-Based Deep Learning Approach for Predicting Gastrointestinal Diseases

A deep learning framework for automated classification of gastrointestinal (GI) diseases from endoscopic images, built as a computer-aided diagnosis (CAD) system to support clinicians with early, consistent, and reproducible diagnostic assistance.

> 📄 Published at IEEE: *Endoscopic Image-Based Deep Learning Approach for Predicting Gastrointestinal Diseases*
> Authors: Joel Johnson BV, K Martin Victor (Karunya Institute of Technology and Sciences)

## Overview

Endoscopy is the standard for diagnosing GI conditions such as polyps, ulcers, and colorectal cancer, but interpretation depends heavily on clinician experience and is prone to fatigue and subjective error. This project uses Convolutional Neural Networks (CNNs) with transfer learning to classify endoscopic images automatically and compares three architectures to find the best performer.

## Models Compared

| Model | Test Accuracy |
|---|---|
| **ResNet50** | **84.5%** |
| MobileNetV2 | 80.5% |
| VGG16 | 70.1% |

ResNet50 performed best thanks to its residual (skip) connections, which help it learn deeper, more detailed features. The proposed model also reached **87.6% recall** and an **F1-score of 85.8%**.

## Methodology

1. **Dataset**: [Kvasir](https://www.kaggle.com/datasets/meetnagadia/kvasir-dataset), a multi-class endoscopic image dataset, split 70% train / 15% validation / 15% test.
2. **Preprocessing**: images resized to 224×224, denoised with Gaussian and median filters, and normalized.
3. **Data augmentation**: flips, rotation, zoom, brightness/contrast shifts, and CLAHE, expanding the dataset to about 40,000 images.
4. **Model development**: transfer learning with pre-trained ResNet50, VGG16, and MobileNetV2, with the final layer replaced by a softmax classifier.
5. **Training and tuning**: GPU training with grid-search hyperparameter tuning (learning rate, batch size, epochs).
6. **Evaluation**: accuracy, precision, recall, F1-score, and confusion matrix.

## Tech Stack

Python · TensorFlow/Keras · CNNs (ResNet50, VGG16, MobileNetV2) · Kvasir Dataset

## Future Work

- Train on larger, multi-center clinical datasets for better generalization
- Add explainable AI (e.g., Grad-CAM) to highlight the image regions driving each prediction
- Explore hybrid ResNet + Transformer architectures
- Optimize for real-time deployment in clinical settings

## Citation

```
Joel Johnson BV, K Martin Victor. "Endoscopic Image-Based Deep Learning Approach for
Predicting Gastrointestinal Diseases." IEEE Conference, 2025.
Paper Published in IEEE - [https://ieeexplore.ieee.org/abstract/document/11382902]
```
<img width="857" height="433" alt="Screenshot 2026-04-28 224105" src="https://github.com/user-attachments/assets/b8fd36a6-fba0-4427-86ad-5d94fe2475c5" />
<img width="527" height="207" alt="Screenshot 2025-09-05 142858" src="https://github.com/user-attachments/assets/1b600519-d6e1-4c04-8c76-fdee96da31f2" />
<img width="573" height="240" alt="Screenshot 2025-09-05 190944" src="https://github.com/user-attachments/assets/b5e4427b-80e9-4ffa-8c9b-0de867131b89" />
<img width="186" height="150" alt="Screenshot 2025-09-10 010348" src="https://github.com/user-attachments/assets/3c4d70a2-5fed-4a94-8d47-8fced46a1b41" />
<img width="117" height="125" alt="Screenshot 2025-09-10 013706" src="https://github.com/user-attachments/assets/5419022d-7084-4ff7-b9f4-5c0d2e164d40" />
<img width="1258" height="494" alt="Screenshot 2026-03-03 233934" src="https://github.com/user-attachments/assets/f357b31d-5d56-4b6e-bb70-90c19c1e2022" />

