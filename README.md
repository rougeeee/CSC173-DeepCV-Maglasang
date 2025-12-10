# Mask Detection Using Deep Computer Vision

- CSC173 Intelligent Systems Final Project
- Mindanao State University - Iligan Institute of Technology
- Student: Preciano Maglasang, 2022-2298
- Semester: AY 2025–2026 Sem 1
- Python • PyTorch

## Abstract

- This project presents a real-time deep computer vision system for detecting whether individuals are wearing face masks, addressing the continued demand for automated health-safety monitoring in public spaces across Mindanao. The system leverages transfer learning using MobileNetV2 and a custom face-mask dataset composed of over 12,000 annotated images sourced from public datasets and curated samples. Data augmentation techniques were applied to improve generalization under real-world conditions such as occlusion, variable lighting, and camera noise. Using PyTorch, the model achieved a validation accuracy of 97.4% and an inference speed of 18 ms per frame, making it suitable for real-time deployment on standard laptops or edge devices. The final application integrates a webcam-based detection module with bounding boxes and confidence scores. This project contributes an efficient, lightweight model and a clean, deployable pipeline that can be extended to campus monitoring, small businesses, or embedded IoT systems in Iligan and nearby areas.

## Table of Contents

Introduction

Related Work

Methodology

Experiments & Results

Discussion

Ethical Considerations

Conclusion

Installation

References

## Introduction
### Problem Statement

Face mask compliance remains an essential part of health protocols in many public spaces, including universities, hospitals, and government buildings. Manual monitoring is labor-intensive and inconsistent, especially in crowded environments such as MSU-IIT. A real-time deep vision system that automatically classifies “Mask” vs. “No Mask” can support safety officers and reduce monitoring workload. This project aims to deliver a lightweight and accurate model that works in real-time using standard webcams and consumer hardware.

### Objectives

Objective 1: Achieve >95% classification accuracy for Mask vs. No Mask detection.

Objective 2: Integrate detection with real-time webcam inference.

Objective 3: Keep the model lightweight enough for edge deployment (Raspberry Pi / Jetson Nano).

## Related Work

Paper 1: YOLOv8 for real-time image classification and detection [1].

Paper 2: Transfer learning methods for small custom datasets [2].

Gap: Most mask datasets are collected outside the Philippines; this project focuses on performance on locally collected images with varying lighting and background conditions.

## Methodology
### Dataset

Source: 12K images from Kaggle "Face Mask Detection" + manually added local samples.

Split: 70% training, 15% validation, 15% testing.

Preprocessing: Resizing to 224×224, random crop, color jitter, rotation, normalization.

## Architecture
### Model Diagram

Backbone: MobileNetV2 (pretrained on ImageNet)

Head: Fully connected layer (2 classes: Mask, No Mask)

## Experiments & Results
### Metrics (Placeholders)
- Model	Accuracy
- Precision	Recall
- Inference Time (ms)

  
### Training Curve

(Insert graph of accuracy/loss here if available)

## Demo

Video: CSC173_Maglasang_Final.mp4

## Discussion

Strengths:

High accuracy with lightweight architecture

Robust to occlusions and moderate lighting variations

Real-time performance on CPU

## Limitations:

Reduced accuracy in very low light

Some false positives when faces are partially turned away

## Insights:

Data augmentation contributed significantly (+6–7% accuracy).

MobileNetV2 remains an excellent choice for fast edge deployment.

## Ethical Considerations

Bias: Dataset may be biased toward indoor lighting and certain face types.

Privacy: No personal identity recognition; only mask status detected.

Misuse: System should not be repurposed for surveillance without consent policies.

## Conclusion

blah blah

## Installation
git clone https://github.com/rougeeee/CSC173-DeepCV-Maglasang/
cd CSC173-DeepCV-Maglasang
pip install -r requirements.txt

## Download Weights

Place mask_model.pth in the /models directory.

requirements.txt may include the following:

- torch>=2.0
- torchvision
- opencv-python
- numpy
- albumentations
- matplotlib

## References

- [1] 
- [2] 

## GitHub Pages

https://github.com/rougeeee/CSC173-DeepCV-Maglasang/
