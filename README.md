# congenial-octo-potato

# Smoking Detection in Restricted Areas using YOLOv8
<img width="256" height="255" alt="image" src="https://github.com/user-attachments/assets/a295625a-9dd1-4da3-8b05-746d1ce36add" />

## Overview
This project explores an automated **computer vision-based smoking detection system** designed to identify smoking activities in **non-smoking environments** such as campuses, airports, and public facilities.

The system uses **YOLOv8**, a modern real-time object detection model, to detect:
- cigarettes
- smoking-related hand gestures
- people smoking vs not smoking

The goal is to enable automated surveillance systems that can assist security teams in detecting violations efficiently and in real time.

---

## Problem Statement
Manual monitoring of surveillance footage is:
- time-consuming
- prone to human error
- inefficient for real-time enforcement

This project proposes an AI-based solution that automatically detects smoking activities from video streams and images.

---

## Proposed Solution
The system uses **YOLOv8 (You Only Look Once v8)** as the core detection model.

It identifies:
- Person Smoking
- Person Not Smoking
- Potential cigarette-related objects (where applicable)

The model outputs bounding boxes and confidence scores for detected activities.

---

## Key Features
- Real-time object detection
- Smoking vs non-smoking classification
- Bounding box localization
- High-speed inference (suitable for CCTV systems)
- Transfer learning for improved performance
- Lightweight YOLOv8-nano deployment option

---

## Methodology

### 1. Model Selection
The project uses :contentReference[oaicite:0]{index=0} due to its balance of speed and accuracy in real-time detection tasks.

YOLOv8 uses:
- backbone (feature extraction)
- neck (feature fusion)
- detection head (prediction)

It also uses an **anchor-free detection mechanism**, simplifying training and improving efficiency.

---

### 2. Dataset
The dataset used is a **Smoker Detection Dataset**, consisting of:
- 40 training images
- 10 validation images
- 10 test images

Each image is labeled with:
- Person Smoking
- Person Not Smoking

---

### 3. Training Strategy
To improve performance on a small dataset, the following techniques were applied:

- Transfer learning using pretrained YOLOv8 weights
- Adam optimizer for adaptive learning
- Learning rate scheduling (linear decay)
- Early stopping (patience = 10 epochs)

---

### 4. Detection Logic
The system is designed for surveillance use cases:

- High-confidence “Smoking” predictions trigger alerts
- Non-smoking predictions are deprioritized
- Reduces false alarm impact in real deployments

---

## Performance Results

The model achieved:

| Metric | Value |
|--------|-------|
| mAP@0.5 | 0.762 |
| Recall | 0.893 |
| Precision | 0.598 |

Key observation:
- High recall is prioritized to reduce missed smoking incidents (false negatives)

---

## Real-Time Deployment Suitability
YOLOv8 is suitable for deployment in:
- airports
- campuses
- public surveillance systems

Reasons:
- fast inference speed
- lightweight architecture (YOLOv8-nano option)
- low computational requirements
- scalable for edge devices

---

## Limitations

- Small dataset (60 images) limits generalization
- Difficulty distinguishing smoking from similar hand gestures (e.g., phone use)
- Limited robustness in low-light/night conditions

---

## Future Improvements
- Increase dataset size with diverse environments
- Fine-grained annotation (cigarette-only detection)
- Hard negative mining (e.g., phones, pens)
- Night-time and low-light augmentation
- Multi-class smoke vs cigarette vs hand gesture separation

---

## Conclusion
This project demonstrates that YOLOv8 can be effectively used for **real-time smoking detection in surveillance environments**, offering a practical alternative to traditional machine learning approaches.

While current results are promising, performance can be further improved through larger datasets and more refined annotation strategies.
