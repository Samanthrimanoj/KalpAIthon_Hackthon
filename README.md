# KalpAIthon_Hackthon

# 🎯 PixelProof – Deepfake Video Detector

PixelProof is an offline deepfake video detection system that classifies videos as **REAL** or **FAKE** using a pretrained deep learning model. It is designed for hackathons, academic projects, and quick prototype demonstrations.


## 🚨 Problem Statement

With the rapid growth of deepfake technology, it has become easier to generate highly realistic fake videos that can impersonate individuals.

This creates serious risks such as:
- Financial fraud (fake KYC verification)
- Identity theft
- Spread of misinformation
- Social media manipulation

There is a need for a **fast, reliable, and offline solution** that can detect whether a video is real or fake without requiring heavy infrastructure or internet access.

## 📖 Description

PixelProof is a lightweight system that analyzes videos frame-by-frame to detect deepfake manipulations.

### 🔍 How it works:
- Accepts a video input
- Extracts frames using OpenCV
- Processes each frame using a pretrained deep learning model
- Classifies each frame as REAL or FAKE
- Uses majority voting to determine the final result

### ⭐ Key Features:
- Fully offline detection
- Fast processing (optimized for short videos)
- Works on standard laptops
- Supports common video formats
- Easy to run in Google Colab or Jupyter Notebook

## 💡 Proposed Solution

PixelProof uses a **Frame-wise CNN Classification Pipeline** to detect deepfake videos.

### ⚙️ Workflow

User Uploads Video
        ↓
Frame Extraction (OpenCV)
        ↓
Frame Preprocessing
        ↓
Pretrained Model
        ↓
Frame-wise Prediction
        ↓
Majority Voting
        ↓
Final Output (REAL / FAKE)

### 🧠 Approach:
- Extract frames at fixed intervals
- Analyze each frame using pretrained CNN models (EfficientNet / ResNet / Xception)
- Detect visual inconsistencies like:
  - Facial distortions
  - Texture anomalies
  - Lighting inconsistencies
- Aggregate predictions to classify the video

### 📊 Output:
- Final Label: REAL / FAKE
- Confidence Score
- Frame-level statistics


## 🧰 Tech Stack

### 💻 Programming Language
- Python 3.x

### 📚 Libraries
- OpenCV
- PyTorch
- Transformers
- NumPy
- Matplotlib
- Pillow

### 🛠️ Platforms
- Google Colab
- Jupyter Notebook
- Anaconda


