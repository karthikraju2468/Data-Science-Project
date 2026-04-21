# Bone Fracture Detection using Deep Learning

## Overview
This project focuses on automated bone fracture detection in X-ray images using deep learning-based object detection models. It compares the performance of Faster R-CNN, YOLOv8, and a custom CNN under the same dataset conditions to evaluate the impact of architecture choice, transfer learning, and data imbalance.

---

## Objectives
- Develop and compare object detection models for fracture detection  
- Analyse performance of two-stage, single-stage, and custom CNN approaches  
- Investigate the effect of class imbalance on model performance  
- Evaluate the benefits of transfer learning in medical imaging  

---

## Models Used
- **Faster R-CNN** (two-stage detector with ResNet50 backbone)  
- **YOLOv8** (single-stage real-time detector)  
- **Custom CNN** (trained from scratch without pretrained weights)  

---

## Dataset
The dataset consists of X-ray images with 7 fracture-related classes:

- Elbow positive  
- Fingers positive  
- Forearm fracture  
- Humerus fracture  
- Humerus  
- Shoulder fracture  
- Wrist positive  

### Dataset Split
- Training: 1446 images  
- Validation: 531 images  
- Testing: 83 images  

---

## Data Preprocessing
- Removed images without annotations  
- Redistributed training data to validation set  
- Resized all images to **512 × 512**  
- Converted annotations from YOLO format to Pascal VOC format  
- Applied data augmentation (training only):
  - Horizontal flip  
  - Brightness and contrast adjustment  
  - CLAHE  
  - Affine transformations  
  - Gaussian blur  
- Normalisation using ImageNet mean and standard deviation  

---

## Evaluation Metrics
- Intersection over Union (IoU ≥ 0.5)  
- Precision  
- Recall  
- F1-score  

---

## Results

| Model         | Precision | Recall | F1 Score |
|--------------|----------|--------|---------|
| YOLOv8       | 0.634    | 0.519  | 0.566   |
| Faster R-CNN | 0.267    | 0.236  | 0.240   |
| Custom CNN   | -        | -      | 0.056   |

---

## Key Findings
- YOLOv8 achieved the best overall performance  
- Faster R-CNN struggled with limited and imbalanced data  
- Custom CNN performed poorly due to lack of transfer learning  
- Class imbalance significantly impacted detection of rare fractures  

---

## Installation

```bash
git clone https://github.com/your-username/bone-fracture-detection.git
cd bone-fracture-detection
pip install -r requirements.txt
