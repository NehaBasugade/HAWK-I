# Real-Time Object Detection + Voice Alerts (YOLOv8)

A real-time computer vision project that uses **YOLOv8 (Ultralytics)** with a webcam to detect everyday objects and provide **audio feedback** using text-to-speech. Along with detection, the system estimates an **approximate distance** from the camera and gives a simple direction cue (**left / right / ahead**).  
I built this project to better understand how modern vision models work in real-time settings and how to turn model outputs into a usable feature.

## What it does
- Detects objects from **live webcam frames**
- Draws **bounding boxes**, labels, and confidence
- Estimates **approx. distance** using bounding box width + assumed real-world object widths
- Announces objects using **voice alerts** when they are within a threshold distance

## Data / Model
- Uses **YOLOv8n** pre-trained on the **COCO dataset** (80 object classes)
- Input is **real-time video frames** from the webcam (no separate dataset needed to run)
- Distance estimate is based on a simple camera-geometry idea + a manual object-width map (`classNamesWidth`)

## Tech Stack
- Python
- Ultralytics YOLOv8
- OpenCV
- gTTS (Text-to-Speech)
- playsound

## What I learned
- How real-time object detection pipelines work (capture → inference → post-processing → display)
- Interpreting YOLO outputs (classes, confidence, bounding boxes)
- Turning model predictions into a usable interaction (audio + direction cues)
- Trade-offs between speed and accuracy (using lightweight YOLOv8n for real-time performance)
- Why calibration matters for distance estimation and how to improve it

## Setup
Install dependencies:
```bash
pip install ultralytics opencv-python gTTS playsound
