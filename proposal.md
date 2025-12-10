# CSC173 Deep Computer Vision Project Proposal

- Student: Preciano Maglasang, CSC171
- Date: December 11, 2025

## 1. Project Title

Face Mask Detection Using Deep Computer Vision

## 2. Problem Statement

Face mask monitoring remains important in many public spaces such as universities, hospitals, and community centers. Manual monitoring is labor-intensive and inconsistent, especially in moderately crowded environments like MSU-IIT. This project aims to develop a lightweight deep computer vision system capable of detecting whether individuals are wearing face masks or not. The solution is locally relevant because it can support safety guidelines, automate monitoring, and assist personnel in maintaining compliance during health-sensitive periods.

## 3. Objectives

- Develop and train a deep computer vision model that achieves high accuracy (>95%) in classifying “Mask” vs “No Mask.”

- Implement a complete training pipeline including dataset preparation, preprocessing, augmentation, training, validation, and evaluation.

- Deploy the trained model in a real-time webcam application capable of running on consumer hardware or low-cost edge devices.

## 4. Dataset Plan

Source: Kaggle “Face Mask Detection Dataset” (~12,000 images) + optional small local samples.

Classes:

  - Mask

  - No Mask

Acquisition: Download public dataset from Kaggle; capture additional local photos if needed to improve performance under varying lighting and backgrounds.

## 5. Technical Approach
### Architecture Sketch

Input Image → Preprocessing → MobileNetV2 Backbone → Classification Head → Mask/No Mask Output

### Model:

- MobileNetV2 (fine-tuned)
Reason: Fast, efficient, ideal for real-time and edge deployment.

### Framework:

PyTorch

### Hardware:

- Google Colab GPU (T4/L4) for training
- Local laptop CPU for real-time inference

## 6. Expected Challenges & Mitigations

- Challenge: Small or imbalanced dataset
  - Solution: Apply strong augmentations (flip, brightness, rotation, color jitter) to increase diversity.

- Challenge: Lighting variations during real-time detection
  - Solution: Use normalization and brightness-based augmentation; adjust preprocessing pipeline.

- Challenge: Model may struggle with partially occluded faces
  - Solution: Include occlusion-focused augmentation and additional sample collection if necessary.

- Challenge: Real-time performance on CPU
  - Solution: Use a lightweight architecture (MobileNetV2) and optimize frame processing.
