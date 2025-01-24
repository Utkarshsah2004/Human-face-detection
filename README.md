# Face detection

This project demonstrates how to read a video stream from a camera, process each frame to detect faces using Haar cascades, and display the processed frames in real-time using OpenCV.

## Requirements

To run this script, ensure you have the following installed:

1. Python
2. OpenCV library (cv2)

You can install OpenCV using pip:
```bash
pip install opencv-python
```

Additionally, download the `haarcascade_frontalface_alt.xml` file from OpenCV's official repository or include it in the project directory.

## How It Works

1. **Initialize Video Capture**:
   - The script uses `cv2.VideoCapture(0)` to start capturing video from the default camera.

2. **Load Haar Cascade**:
   - The Haar cascade for face detection is loaded using `cv2.CascadeClassifier`. Ensure the XML file is present in the working directory.

3. **Process Frames**:
   - Each frame is converted to grayscale for efficient processing.
   - Faces are detected using `detectMultiScale`.

4. **Draw Bounding Boxes**:
   - For each detected face, a rectangle is drawn on the frame.

5. **Display Frames**:
   - The processed frame is displayed in a window named `Video Frame`.

6. **Stop the Stream**:
   - The script listens for the 'q' key to terminate the loop and release resources.

## Usage

1. Save the script and ensure the `haarcascade_frontalface_alt.xml` file is in the same directory.
2. Run the script:
   ```bash
   python script_name.py
   ```
3. A window will open showing the live video feed with detected faces highlighted by rectangles.
4. Press 'q' to exit the program.

## Notes

- The `detectMultiScale` function parameters can be adjusted to improve face detection accuracy:
  - `scaleFactor`: Specifies how much the image size is reduced at each image scale.
  - `minNeighbors`: Specifies how many neighbors each candidate rectangle should have to retain it.

- Ensure proper lighting conditions for better face detection results.

- If the default camera does not work, check if the correct device index is used in `cv2.VideoCapture()`.

## References

- [OpenCV Documentation](https://docs.opencv.org/)
- [Haar Cascade Classifier Information](https://docs.opencv.org/3.4/db/d28/tutorial_cascade_classifier.html)

