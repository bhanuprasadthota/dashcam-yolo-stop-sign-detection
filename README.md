# DashCam YOLOv3 Stop Sign Detection

Guide and configuration for building a real-time stop sign detector using a pretrained YOLOv3 model on dash camera footage with OpenCV.

## Overview

This project demonstrates how to apply YOLOv3 object detection to live or recorded dash camera footage to detect stop signs. It uses the COCO-pretrained YOLOv3 weights and processes frames in real time with bounding box overlays.

## How It Works

1. Load the YOLOv3 model using the provided `yolov3.cfg` and COCO class labels (`coco.names`)
2. Load dash camera video footage (file path or live feed)
3. Run object detection on each frame
4. Filter detections for the `stop sign` class
5. Apply non-maximum suppression to remove duplicate boxes
6. Overlay bounding boxes and display annotated video

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| YOLOv3 | Pretrained object detection model |
| OpenCV | Video capture and frame processing |
| NumPy | Array operations |

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/bhanuprasadthota/dashcam-yolo-stop-sign-detection.git
   cd dashcam-yolo-stop-sign-detection
   ```

2. Install dependencies:
   ```bash
   pip install opencv-python-headless numpy
   ```

3. Download YOLOv3 weights:
   ```bash
   wget https://pjreddie.com/media/files/yolov3.weights
   ```

4. Run detection on your footage:
   ```python
   import cv2, numpy as np

   net = cv2.dnn.readNet(yolov3.weights, yolov3.cfg)
   with open(coco.names) as f:
       classes = f.read().strip().split(
)

   cap = cv2.VideoCapture(your_dashcam_video.mp4)
   # ... detection loop
   ```

## Files

```
├── yolov3.cfg    # YOLOv3 model architecture config
├── coco.names    # 80 COCO class labels (includes stop sign)
└── README.md     # This file
```

> Note: `yolov3.weights` is not included due to file size. Download separately from pjreddie.com.

## License

MIT License — see [LICENSE](LICENSE) for details.
