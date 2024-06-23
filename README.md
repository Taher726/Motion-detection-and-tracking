# Motion Detection with OpenCV

This project demonstrates a simple motion detection system using OpenCV. The script processes video frames to detect and highlight areas of motion.

## Requirements

- Python 3.x
- OpenCV

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/your-username/your-repository-name.git
    ```

2. Navigate to the project directory:

    ```bash
    cd your-repository-name
    ```

3. Install the required packages:

    ```bash
    pip install opencv-python
    ```

## Usage

1. Place your video file (`vtest.avi` or any other video file) in the project directory.
2. Run the script:

    ```bash
    python motion_detection.py
    ```

## Script Explanation

The script reads frames from a video file and detects motion between consecutive frames. It highlights the areas of motion with rectangles.

- `cv2.VideoCapture("vtest.avi")`: Opens the video file.
- `cv2.absdiff(frame1, frame2)`: Computes the absolute difference between two consecutive frames.
- `cv2.cvtColor(diff, cv2.COLOR_BGR2GRAY)`: Converts the difference image to grayscale.
- `cv2.GaussianBlur(gray, (5, 5), 0)`: Applies Gaussian blur to the grayscale image.
- `cv2.threshold(blur, 20, 255, cv2.THRESH_BINARY)`: Applies a binary threshold to the blurred image.
- `cv2.dilate(thresh, None, iterations=3)`: Dilates the thresholded image to fill in gaps.
- `cv2.findContours(dilated, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)`: Finds contours in the dilated image.
- `cv2.boundingRect(contour)`: Computes the bounding rectangle for each contour.
- `cv2.rectangle(frame1, (x, y), (x+w, y+h), (0, 255, 0), 2)`: Draws rectangles around areas of motion.

## Acknowledgements

This project uses OpenCV, an open-source computer vision and machine learning software library.

