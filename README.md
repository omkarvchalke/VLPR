# Vehicle License Plate Recognition System


# Vehicle License Plate Recognition Using Neural Networks

A deep learning–based Vehicle License Plate Recognition (VLPR) system designed to automatically detect vehicle license plates from images and recognize the alphanumeric characters present on them. The project combines **YOLO-based license plate detection** with **OCR-based character recognition** to support use cases such as toll automation, parking management, traffic monitoring, access control, and vehicle identification. 

## Overview

With the growing number of vehicles on roads, manual identification of license plates has become inefficient for applications such as traffic rule enforcement, toll collection, parking billing, and security monitoring. This project proposes a lightweight and accurate framework for **automatic license plate detection and recognition** using **Convolutional Neural Networks (CNNs)** and **Optical Character Recognition (OCR)**. 

The system works in five major stages:

1. Image Acquisition  
2. License Plate Detection  
3. License Plate Extraction  
4. License Plate Segmentation  
5. Character Recognition 

---

## Problem Statement

Traffic control and vehicle owner identification are major challenges, especially when vehicles are moving at high speed, crossing regional boundaries, or using fake number plates. Retrieving a plate number manually from a moving vehicle is difficult, which makes enforcement and tracking inefficient. This project addresses that challenge by building an **Automatic Number Plate Recognition (ANPR)** system that detects and recognizes the vehicle registration number directly from an image. 

---

## Proposed Framework

The proposed framework follows the pipeline below:

- **Image Acquisition** – Capture the image of a vehicle
- **License Plate Detection** – Detect the license plate using an object detection model
- **License Plate Extraction** – Crop the detected plate region
- **License Plate Segmentation** – Segment the characters from the plate
- **Character Recognition** – Recognize letters and digits using OCR / neural methods 

---

## Tech Stack

- **Python**
- **YOLO / YOLOv4** for license plate detection
- **CNN** for image-based feature learning
- **OpenCV** for image preprocessing and segmentation
- **Tesseract OCR** for character recognition
- **TensorFlow / Keras**
- **Darknet** for YOLO model training 

---

## Methodology

### 1. License Plate Detection
For plate detection, the project uses **YOLO (You Only Look Once)**, a real-time object detection algorithm based on convolutional neural networks. YOLO treats object detection as a regression problem and predicts bounding boxes and class probabilities in a single pass, making it suitable for fast plate localization. 

### 2. Data Annotation
A dataset of approximately **1500 car images** was collected, and bounding boxes were created for the class **"License Plate"**. Annotation coordinates were converted into YOLO-compatible format for training. 

### 3. OCR-Based Recognition
After the license plate is detected and extracted, the image is preprocessed and passed through **OpenCV** and **Tesseract OCR** for character segmentation and recognition. OCR converts the visual plate characters into machine-readable text. 

### 4. Image Preprocessing
The recognition workflow may include:
- grayscale conversion
- binarization
- Gaussian blur
- contour detection
- thresholding
- segmentation of individual characters 

---

## Why YOLO?

YOLO is well suited for this task because it offers strong real-time performance for object detection. The project report compares common architectures and highlights **YOLOv4** as the selected model because it delivers better accuracy and speed than several alternatives used in the study. 

### Comparative Analysis

| Architecture | mAP Accuracy | Speed (FPS) |
|---|---:|---:|
| YOLOv4 | 47.5 | 73 |
| YOLOv3 | 31.0 | 34 |
| SSD512 | 35.1 | 39 |
| Mask R-CNN | 40.3 | 3 |
| Faster R-CNN | 36.2 | 6 |
| Fast R-CNN | 35.9 | 0.5 |

The implementation notes that **YOLOv4 provided about 10% more accuracy and 12% more speed than YOLOv3** in the project setup.

---

## Applications

This system can be applied in multiple intelligent transportation and security scenarios, including:

- **Automatic Toll Collection**
- **Parking Management Systems**
- **Traffic Rule Enforcement**
- **Speed Violation Monitoring**
- **Access Control**
- **Crime Detection / Stolen Vehicle Tracking** 

---

## Results

The project successfully demonstrates real-time vehicle license plate detection and recognition using **YOLOv4 + OCR**. The output includes a bounding box around the detected license plate along with the recognized license number, enabling downstream applications such as toll systems, parking management, and surveillance workflows.

Examples shown in the report and presentation include:

- License plate detection on **CCTV footage**
- Recognition for **parking management**
- Recognition for **toll management** 

---

## Limitations

The report notes that license plate recognition systems can face reduced accuracy under conditions such as:

- rainfall
- fog
- inclined vehicle images
- low-quality images
- poor illumination / noisy inputs 

---

## Future Scope

Potential future enhancements include:

- improving robustness under challenging weather and lighting conditions
- handling more plate formats and regions
- extending from image-based input to large-scale live video feeds
- increasing OCR accuracy for blurred and angled plates
- integrating the system with centralized vehicle databases and alert systems

These directions are consistent with the report’s scope around traffic management, tolling, parking, and security automation. 

---

## System Requirements

- Labelled vehicle image dataset
- YOLO-compatible annotation files
- Darknet for YOLO training
- Python environment with:
  - TensorFlow / Keras
  - OpenCV
  - Tesseract OCR

