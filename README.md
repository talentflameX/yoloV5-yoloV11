# yoloV5-yoloV11
# YOLO People Detection from Video

This project uses YOLOv5 and YOLOv11 to detect people in a video while experimenting with different resolutions to improve speed and efficiency.

## Features
- Detects and counts people in each frame.
- Compares YOLOv5 and YOLOv11 in terms of inference speed and detection accuracy.
- Supports video input with adjustable resolution.
- Outputs performance metrics including average inference time and average people detected per frame.

## Requirements
- Python 3.8+
- OpenCV (`cv2`)
- `ultralytics` for YOLO models
- `time` module

## Installation
```sh
pip install opencv-python ultralytics
```

## Usage
1. Place your video file in the project directory.
2. Update `video_path` in the script to match your file.
3. Run the script:
   ```sh
   python yolo_video_detection.py
   ```

## Adjusting Resolution
YOLO requires image dimensions to be multiples of 32. To modify resolution, update the `imgsz` parameter in the YOLO model call:
```python
yolo5_model = YOLO("yolov5su.pt")
yolo11_model = YOLO("yolo11n.pt")

results5 = yolo5_model(frame_rgb, imgsz=[256, 448])
results11 = yolo11_model(frame_rgb, imgsz=[256, 448])
```

## Performance Metrics
At the end of execution, the script prints:
- **YOLOv5 - Avg Inference Time & People Count**
- **YOLOv11 - Avg Inference Time & People Count**

Example Output:
```
YOLOv5 - Avg Inference Time: 0.2375 sec, Avg People Detected: 11.68
YOLOv11 - Avg Inference Time: 0.0943 sec, Avg People Detected: 11.27
```

## Notes
- Lower resolutions (e.g., `256x448`, `224x384`) improve speed but may affect accuracy.
- Frames are processed in RGB format as required by YOLO.

## License
MIT License
