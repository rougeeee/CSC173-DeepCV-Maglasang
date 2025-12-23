# Mask Detection Using Deep Computer Vision

- CSC173 Intelligent Systems Final Project
- Mindanao State University - Iligan Institute of Technology
- Student: Preciano Maglasang, 2022-2298
- Semester: AY 2025–2026 Sem 1
- Python • PyTorch

## Abstract

This project presents a deep computer vision system for automated face mask detection, addressing the continued need for efficient health-safety monitoring in public spaces across Mindanao. Manual enforcement of mask compliance is labor-intensive and prone to inconsistency, particularly in crowded environments such as universities, hospitals, and government facilities. To mitigate these challenges, a lightweight yet accurate image classification model was developed to distinguish between “Mask” and “No Mask” cases in real time.

The system utilizes a transfer-learning approach based on a pretrained MobileNetV2 architecture, fine-tuned using a publicly available Kaggle face mask dataset supplemented with locally collected images. Images were preprocessed through resizing, normalization, and data augmentation techniques to improve robustness against lighting variation and partial occlusions. The dataset was split into training, validation, and testing sets to ensure reliable performance evaluation.

Experimental results demonstrate that the proposed model achieves high classification accuracy while maintaining fast inference speeds suitable for deployment on consumer-grade hardware. The project highlights the effectiveness of lightweight convolutional neural networks for real-time computer vision tasks and demonstrates their applicability in local health-monitoring scenarios. Future improvements include deployment on edge devices and expansion of the dataset to improve performance in low-light environments.
  
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

Face mask compliance remains an important component of public health protocols in many shared spaces, including educational institutions such as MSU-IIT. Relying on manual monitoring is inefficient and difficult to sustain, especially during peak hours and large gatherings. An automated vision-based system capable of accurately identifying whether individuals are wearing face masks can assist safety personnel and reduce monitoring workload. This project focuses on developing a real-time, deep learning-based solution that is both accurate and computationally efficient.

### Objectives

Objective 1: Achieve >95% classification accuracy for Mask vs. No Mask detection.

Objective 2: Integrate detection with real-time webcam inference.

Objective 3: Keep the model lightweight enough for edge deployment (Raspberry Pi / Jetson Nano).

## Related Work

YOLOv8 for Real-Time Detection: Recent work demonstrates the effectiveness of YOLO-based architectures for real-time object detection and classification tasks [1].

Transfer Learning for Small Datasets: Prior studies show that fine-tuning pretrained convolutional neural networks significantly improves performance on limited datasets [2].

Gap: Most existing face mask datasets and evaluations are conducted outside the Philippine context. This project explores model performance under locally observed conditions, including varied lighting, backgrounds, and camera quality.

## Methodology
### Dataset

Source: Kaggle “Face Mask Detection” dataset (~12,000 images) with additional locally collected samples

Classes: with_mask, without_mask

Data Split:

- 70% Training
- 15% Validation
- 15% Testing

Preprocessing:

- Resizing to 224 × 224
- Random horizontal flip
- Color jitter and rotation
- ImageNet normalization

## Architecture
### Model Diagram

**Backbone:** MobileNetV2 (pretrained on ImageNet)

**Classification Head:** Fully connected layer with 2 output neurons

**Loss Function:** Cross-Entropy Loss

**Optimizer:** Adam

The MobileNetV2 architecture was selected due to its balance between accuracy and computational efficiency, making it suitable for real-time and edge-based applications.

## Experiments & Results
### Metrics 
- Model	Accuracy
- Precision	Recall
- Inference Time (ms)

  
### Training Curve

<img width="1242" height="487" alt="image" src="https://github.com/user-attachments/assets/34f9694e-40e5-4fdf-b1a3-bbc918aea6f6" />

## Demo

Video: [CSC173_Maglasang_Final.mp4](https://drive.google.com/drive/folders/1TC3tsixUenWse2WRwbFpcBSJwAeeXb2O?usp=sharing)

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

This project successfully demonstrates the feasibility of using deep computer vision for real-time face mask detection in local public environments. By leveraging transfer learning and a lightweight CNN architecture, the system achieves high accuracy while remaining suitable for deployment on consumer hardware. Future work includes expanding the dataset with more local samples, improving low-light robustness, and deploying the system on embedded edge devices for real-world use.

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

[1] Jocher, G., et al. YOLOv8: Real-Time Object Detection, Ultralytics, 2023.

[2] Deng, J., et al. ImageNet: A Large-Scale Hierarchical Image Database, CVPR, 2009.

## GitHub Pages

https://github.com/rougeeee/CSC173-DeepCV-Maglasang/
