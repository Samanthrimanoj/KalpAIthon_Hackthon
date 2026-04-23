# KalpAIthon_Hackthon

# PixelProof – Deepfake Video Detector

PixelProof is an offline deepfake video detection system designed to classify short videos as **REAL** or **FAKE**. It is optimized for hackathons, academic projects, and prototype demonstrations where speed, simplicity, and local execution are important.

The system analyzes uploaded videos frame-by-frame using a pretrained deep learning model and combines frame predictions to generate a final result.

---

# Table of Contents

1. Project Overview
2. Problem Statement
3. Objectives
4. Key Features
5. System Workflow
6. Algorithm Used
7. Tech Stack
8. Folder Structure
9. Installation
10. How to Run
11. Input / Output Format
12. Performance Targets
13. Limitations
14. Future Improvements
15. Use Cases
16. Team / Author
17. License

---

# 1. Project Overview

Deepfake videos are AI-generated manipulated videos that make people appear to say or do things they never did. These videos are increasingly realistic and can be used for fraud, misinformation, identity abuse, and reputational harm.

PixelProof provides a lightweight local solution to detect suspicious videos quickly without requiring internet access or expensive infrastructure.

---

# 2. Problem Statement

Create a practical solution that can detect whether a short uploaded video is real or fake under the following constraints:

* Must run on a normal laptop
* No internet/API calls during testing
* Process a 10-second video in under 10 seconds
* Reasonable baseline accuracy is acceptable
* Easy to demo in a hackathon or project review

---

# 3. Objectives

PixelProof is built to:

* Accept a video file as input
* Extract meaningful frames
* Analyze frames for deepfake artifacts
* Predict REAL or FAKE
* Display confidence score
* Run fully offline

---

# 4. Key Features

* Offline video detection
* Fast inference on short videos
* Uses pretrained deep learning model
* Supports common video formats
* Frame-level analysis
* Final majority-vote decision
* Easy to deploy in Google Colab or local Python environment

---

# 5. System Workflow

```text
User Uploads Video
        ↓
Frame Extraction using OpenCV
        ↓
Frame Preprocessing
        ↓
Pretrained Deepfake Detection Model
        ↓
REAL / FAKE prediction for each frame
        ↓
Majority Voting
        ↓
Final Video Classification
```

---

# 6. Algorithm Used

PixelProof uses a **Frame-wise CNN Classification Pipeline**.

## Step 1: Frame Extraction

The uploaded video is processed using OpenCV:

```python
cv2.VideoCapture()
```

Frames are extracted at fixed intervals (for example every 10th or 15th frame).

## Step 2: Frame Classification

Each extracted frame is passed through a pretrained deep learning model such as:

* EfficientNet
* XceptionNet
* ResNet
* Hugging Face pretrained deepfake classifier

The model predicts whether the frame appears REAL or FAKE.

## Step 3: Majority Voting

If most frames are classified as fake, the final video is labeled FAKE.

Example:

```text
REAL Frames = 8
FAKE Frames = 14

Final Result = FAKE VIDEO
```

---

# 7. Tech Stack

## Programming Language

* Python 3.x

## Libraries

* OpenCV
* PyTorch
* Transformers
* NumPy
* Matplotlib
* Pillow

## Development Platforms

* Google Colab
* Anaconda
* Jupyter

---

# 8. Folder Structure

```text
PixelProof/
│── main.ipynb
│── best_model.pth
│── sample_videos/
│   ├── real.mp4
│   └── fake.mp4
│── outputs/
│   ├── result_frames/
│   └── reports/
│── README.md
```

---

# 9. Installation

## Install Dependencies

```bash
pip install torch torchvision transformers opencv-python pillow matplotlib numpy
```

---

# 10. How to Run

## In Google Colab

1. Open Colab
2. Upload notebook file
3. Run all cells
4. Upload video when prompted

## In Local Jupyter Notebook

```bash
jupyter notebook
```

Open notebook and run cells.

---

# 11. Input / Output Format

## Input

Supported formats:

* `.mp4`
* `.avi`
* `.mov`

## Output

```text
REAL VIDEO
```

or

```text
FAKE VIDEO
```

Example:

```text
REAL Frames : 7
FAKE Frames : 15

Final Result : FAKE VIDEO
Confidence : 68%
```

---

# 12. Performance Targets

For a standard laptop:

* 10-second video processed in under 10 seconds
* Lightweight model preferred
* Moderate CPU performance supported
* Faster with GPU acceleration

---

# 13. Limitations

* Very high-quality deepfakes may evade detection
* Low-light or blurry videos reduce accuracy
* Side-profile faces may be harder to classify
* Long videos increase processing time

---

# 14. Future Improvements

* Real-time webcam detection
* Audio deepfake detection
* Explainable AI heatmaps
* Browser-based interface
* Mobile app deployment
* Ensemble models for higher accuracy

---

# 15. Use Cases

* Fake news verification
* Social media moderation
* Journalism fact-checking
* Identity fraud prevention
* Academic research
* Digital forensics

---

# 16. Team / Author

Project Name: **PixelProof**

Developed by: Sampurna Banerjee

---

# 17. License

This project is intended for academic, educational, and research use only.

Use responsibly and ethically.

---

# Quick Demo Script

```text
1. Upload suspicious video
2. System extracts frames
3. AI checks each frame
4. Fake frames counted
5. Final result shown instantly
```

---

# Conclusion

PixelProof demonstrates how deep learning and computer vision can be used to combat AI-generated misinformation through fast, accessible, and offline deepfake detection.
