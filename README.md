# YOLO Image and Object Detection Project

This project demonstrates the use of YOLOv8 for detecting humans and objects in images. The model takes an input image, identifies objects within it, and draws bounding boxes around the detected objects with labels and confidence scores.

## Features
- Detects multiple objects in a single image using YOLOv8.
- Draws bounding boxes around detected objects.
- Displays labels and confidence scores for each detected object.

## Prerequisites
To run this project, ensure the following requirements are met:

- Python 3.9.1
- Required Python libraries:
  - OpenCV
  - NumPy
  - Ultralytics (for YOLOv8)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/yolo-image-detection.git
   cd yolo-image-detection
   ```

2. Install the required libraries:
   ```bash
   pip install opencv-python-headless numpy ultralytics
   ```

3. Ensure the YOLOv8 weights file (`yolov8n.pt`) is downloaded. This will happen automatically when you run the script for the first time.

## Usage

1. Place the image you want to process in the project directory.
2. Update the `image_path` variable in the script to the name or path of your image file.
3. Run the script:
   ```bash
   python H&O.py
   ```

4. The script will display:
   - The original image with bounding boxes and labels drawn around detected objects.

## File Structure

```
yolo-image-detection/
|-- H&O.py          # Main script for object detection
|-- requirements.txt # Dependencies list (optional)
|-- 2h&0.jpeg       # Sample image (replace with your own image)
```

## Code Overview

1. **Input Validation**: The script ensures the provided image path is valid.
2. **Image Loading**: The image is read and converted to RGB format.
3. **YOLO Inference**: YOLOv8 detects objects in the image.
4. **Drawing Bounding Boxes**: Detected objects are outlined with bounding boxes, and their labels and confidence scores are displayed.
5. **Output Display**: The processed image is displayed using OpenCV.

## Example Output

When you run the script on an image, you'll see:
- Bounding boxes around detected objects.
- Labels with confidence scores for each detection.

Example:
![Sample Output](example-output.png)

## Dependencies

- [OpenCV](https://opencv.org/)
- [NumPy](https://numpy.org/)
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)

## Troubleshooting

- **Error: Image file not found**: Ensure the `image_path` is correct and the file exists.
- **Error: Could not read image**: Verify the image format is supported.
- **YOLOv8 weights file not found**: Ensure the `yolov8n.pt` weights file is downloaded.

## Contributions
Contributions are welcome! Feel free to fork the repository and submit pull requests.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments
- [YOLOv8](https://github.com/ultralytics/ultralytics)
- OpenCV and NumPy communities

