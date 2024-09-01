# Hand Gesture Volume Controller

This project implements a hand gesture-based volume control system using Python. The application leverages OpenCV, MediaPipe, and macOS's built-in AppleScript functionality to detect hand gestures via a webcam and adjust the system volume accordingly.

## Features

- **Real-time Hand Detection**: Uses the MediaPipe library to detect and track hand landmarks in real-time through a webcam feed.
- **Gesture-based Volume Control**: Calculates the distance between the thumb and index finger to control the system volume. The closer the fingers are, the lower the volume; the farther apart, the higher the volume.
- **Cross-platform Capabilities**: While originally designed for Windows (using `pycaw` for volume control), this version is adapted for macOS using AppleScript commands for volume control.

## How It Works

1. **Hand Detection and Tracking**:
   - The application initializes MediaPipe's hand tracking module, which detects and tracks the position of hands in the webcam feed.
   - It identifies specific landmarks on the hand, such as the tips of the thumb and index finger.

2. **Distance Calculation**:
   - The Euclidean distance between the thumb and index finger is calculated. This distance acts as the control parameter for adjusting the volume.

3. **Volume Mapping**:
   - The calculated distance is mapped to a volume level within a range of 0 to 100, where 0 is mute and 100 is the maximum volume.
   - The system volume is adjusted based on the mapped value using a macOS-compatible approach with AppleScript.

4. **Visual Feedback**:
   - The application provides visual feedback by displaying the webcam feed with landmarks drawn on the detected hand. It also draws circles at the thumb and index finger tips and a line connecting them to visualize the distance being measured.

## Requirements

- **Python 3.x**
- **OpenCV**
- **MediaPipe**
- **Numpy**

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/HandGestureVolumeController.git
   cd HandGestureVolumeController

1. Install the required Python packages:

    pip install opencv-python-headless mediapipe numpy


Future Work
Windows Compatibility: Re-integrate support for Windows using pycaw for volume control.
Enhanced Gesture Recognition: Extend the application to recognize additional gestures for more functionalities like mute/unmute, play/pause, etc.
Cross-platform Support: Investigate ways to support volume control on other platforms like Linux.