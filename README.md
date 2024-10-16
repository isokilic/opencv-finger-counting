# Finger Counting with Computer Vision

This project implements a real-time finger counting application using computer vision techniques. It captures video from a webcam, isolates the hand region, and counts the number of extended fingers.

## Features

- Real-time video processing
- Background subtraction for hand isolation
- Finger counting algorithm
- Live display of finger count and processed frames

## Requirements

- Python 3.6+
- OpenCV (cv2)
- NumPy
- scikit-learn

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/finger-counting-cv.git
   cd finger-counting-cv
   ```

2. Install the required packages:
   ```
   pip install opencv-python numpy scikit-learn
   ```

## Usage

Run the script with:

```
python finger_counting.py
```

- Position your hand in the rectangular region of interest (ROI) displayed on the screen.
- Wait for the background to be captured (about 2 seconds).
- Extend your fingers within the ROI to see the finger count update in real-time.
- Press 'Esc' to exit the application.

## How it Works

1. **Background Subtraction**: The script captures the background for the first 60 frames to create a reference.
2. **Hand Segmentation**: It isolates the hand from the background using frame differencing and thresholding.
3. **Contour Analysis**: The largest contour is assumed to be the hand.
4. **Finger Counting**: A circular ROI is created around the hand, and finger tips are detected as contours crossing this circle.

## Customization

You can adjust the following parameters in the script:

- `roi_top`, `roi_bottom`, `roi_right`, `roi_left`: To change the size and position of the hand ROI.
- `threshold` in the `segment` function: To adjust the sensitivity of hand detection.

## Limitations

- The application works best in consistent lighting conditions.
- It may struggle with complex backgrounds or rapid movements.
- The finger counting algorithm may not be accurate for all hand positions.

## Contributing

Contributions to improve the project are welcome. Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).
