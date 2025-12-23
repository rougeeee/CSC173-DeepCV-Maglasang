# CSC173 Deep Computer Vision Project Progress Report
**Student:** Preciano Maglasang, 2022-2298 

**Date:** [Progress Submission Date]  

**Repository:** https://github.com/rougeeee/CSC173-DeepCV-Maglasang/

**Commits Since Proposal:** [6 commits] | **Last Commit:** [12/23/2025]

## 📊 Current Status
| Milestone | Status | Notes |
|-----------|--------|-------|
| Dataset Acquisition & Preparation |	✅ Completed |	Kaggle dataset fully processed |
| Data Preprocessing & Augmentation |	✅ Completed |	Resize, normalization, augmentation |
| Model Training |	✅ Completed |	MobileNetV2 fully trained |
| Baseline & Final Evaluation	| ✅ Completed	| Metrics finalized |
| Model Fine-tuning	| ✅ Completed	| Optimized learning rate & augmentations |
| Real-time Inference |	✅ Completed	| Webcam-based detection implemented |
| Documentation & Repository	| ✅ Completed	| README, notebook, and report finalized |

## 1. Dataset Summary
**Dataset Source:** Kaggle – Face Mask Detection Dataset

**Total Images:** ~12,000

**Classes:**
  - with_mask

  - without_mask

**Data Split:**

  - Training: 70%

  - Validation: 15%

  - Testing: 15%

# Preprocessing Techniques

- Image resizing to 224 × 224
- Random horizontal flipping
- Color jitter and rotation
- ImageNet normalization

The dataset was randomly split using PyTorch’s random_split to ensure unbiased evaluation.

## 2. Model & Training Summary

<img width="1242" height="487" alt="image" src="https://github.com/user-attachments/assets/a7abe2b5-1146-4c0d-9de6-90b93e438b8a" />

- Architecture: MobileNetV2 (pretrained on ImageNet)
- Framework: PyTorch
- Loss Function: Cross-Entropy Loss
- Optimizer: Adam
- Batch Size: 32
- Epochs: 10

Training converged smoothly with stable validation performance and no significant overfitting observed.

## 3. Final Evaluation Results
| Metric	| Training	| Validation	| Test |
|---------|-----------|-------------|------|
| Accuracy	| ~97%	| ~95%	| ~94% |
| Precision	| ~0.96	| ~0.94	| ~0.93 |
| Recall	| ~0.95	| ~0.93	| ~0.92 |
| Inference Time	| — |	—	| ~15 ms (CPU) |

## 4. Challenges & Resolutions
| Challenge	| Resolution |
|-----------|------------|
| Dataset lacked predefined splits	| Applied controlled random splitting |
| Risk of overfitting	| Used data augmentation & validation monitoring |
| Low-light image misclassification	| Improved via augmentation |
| Real-time speed constraints	| Selected MobileNetV2 for efficiency |

All identified issues were successfully addressed during development.
