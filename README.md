# Face Recognition Project

A real-time face detection and recognition system built for Google Colab that captures photos from webcam, detects faces using Haar Cascade classifiers, and labels them with names.

## Features

- **Real-time Face Detection**: Uses OpenCV's Haar Cascade classifiers for accurate face detection
- **Webcam Integration**: Seamlessly captures photos directly from your webcam in Google Colab
- **Face Labeling**: Automatically labels detected faces with names
- **Bounding Box Visualization**: Draws rectangles around detected faces
- **Image Processing**: Converts between various image formats (JavaScript, OpenCV, PIL)

## Technology Stack

- **Python 3.x**
- **OpenCV**: Computer vision library for face detection
- **face_recognition**: Python library for face recognition
- **NumPy**: Numerical computing
- **PIL (Pillow)**: Image processing
- **JavaScript**: Webcam access in Google Colab
- **Google Colab**: Development environment

## Installation

### Prerequisites
- Google Colab account
- Webcam access permissions

### Setup Instructions

1. **Clone the repository:**
   ```bash
   !git clone https://github.com/ishitaahuja15/face_recognition.git
   %cd face_recognition
   ```

2. **Install required packages:**
   ```bash
   !pip install face_recognition opencv-python pillow numpy
   ```

3. **Import necessary libraries:**
   ```python
   from IPython.display import display, Javascript, Image
   from google.colab.output import eval_js
   from base64 import b64decode, b64encode
   import cv2
   import numpy as np
   import PIL
   import io
   import html
   import time
   ```

## Usage

### Basic Face Detection

1. **Initialize the face detection model:**
   ```python
   face_cascade = cv2.CascadeClassifier(cv2.samples.findFile(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml'))
   ```

2. **Capture and process photo:**
   ```python
   filename = take_photo('captured_photo.jpg', quality=0.8)
   ```

3. **The system will:**
   - Open webcam interface
   - Allow you to capture a photo
   - Detect faces in the image
   - Draw bounding boxes around faces
   - Add name labels below detected faces
   - Save the processed image

### Customization

To customize the name label, modify this line in the `take_photo` function:
```python
name = "Your Name Here, Title"  # Replace with desired name and title
```

## Project Structure

```
face_recognition/
├── README.md
├── requirements.txt
├── src/
│   ├── __init__.py
│   ├── face_detection.py
│   ├── image_processing.py
│   └── webcam_utils.py
├── notebooks/
│   └── face_recognition_demo.ipynb
├── data/
│   ├── captured_images/
│   └── processed_images/
├── models/
│   └── haarcascade_frontalface_default.xml
└── docs/
    └── API_documentation.md
```

## Key Functions

### `js_to_image(js_reply)`
Converts JavaScript webcam capture to OpenCV image format.

**Parameters:**
- `js_reply`: JavaScript object containing base64 encoded image

**Returns:**
- `img`: OpenCV BGR image

### `bbox_to_bytes(bbox_array)`
Converts OpenCV bounding box array to base64 byte string for overlay.

**Parameters:**
- `bbox_array`: Numpy array containing rectangle pixels

**Returns:**
- `bytes`: Base64 encoded image byte string

### `take_photo(filename, quality)`
Main function that captures photo, detects faces, and saves processed image.

**Parameters:**
- `filename`: Output filename (default: 'photo.jpg')
- `quality`: Image quality from 0.0 to 1.0 (default: 0.8)

**Returns:**
- `filename`: Path to saved processed image

## How It Works

1. **Webcam Access**: Uses JavaScript to access the user's webcam through Google Colab
2. **Image Capture**: Captures image when user clicks the "Capture" button
3. **Format Conversion**: Converts JavaScript image data to OpenCV format
4. **Face Detection**: Uses Haar Cascade classifier to detect faces
5. **Visualization**: Draws bounding boxes and name labels on detected faces
6. **Save**: Saves the processed image with annotations

## Troubleshooting

### Common Issues

1. **Webcam Permission Denied**
   - Ensure you've granted webcam permissions to your browser
   - Try refreshing the Colab notebook

2. **Installation Errors**
   - Make sure you're running the code in Google Colab
   - Restart runtime if packages fail to install

3. **Face Detection Not Working**
   - Ensure good lighting conditions
   - Face should be clearly visible and front-facing
   - Try adjusting the `detectMultiScale` parameters

### Performance Tips

- Use good lighting for better face detection
- Keep face centered in the frame
- Ensure stable internet connection for Colab
- Consider image quality vs processing speed trade-offs

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Future Enhancements

- [ ] Multiple face recognition with individual names
- [ ] Real-time video stream processing
- [ ] Face recognition database integration
- [ ] Emotion detection capabilities
- [ ] Face matching against known database
- [ ] Export functionality for different formats

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- OpenCV community for the Haar Cascade classifiers
- Google Colab for providing the development environment
- face_recognition library contributors


⭐ If you found this project helpful, please give it a star on GitHub!