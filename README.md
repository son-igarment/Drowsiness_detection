# Drowsiness Detection System
## Project by Phạm Lê Ngọc Sơn

## Overview
The Drowsiness Detection System monitors user alertness levels, especially while driving, and provides timely warnings to prevent accidents caused by fatigue or drowsiness. The system uses a real-time video feed and machine learning algorithms to analyze facial landmarks and eye blink patterns to detect signs of drowsiness.

## Project Structure
```
Drowsiness_detection/
│
├── drowsinessdetection.py   # Main application script
├── model.py                 # CNN model training script
├── alarm.wav                # Audio alarm file played when drowsiness is detected
│
├── models/                  # Trained model directory
│   └── cnnCat2.h5           # Trained CNN model for eye state classification
│
├── haar cascade files/      # OpenCV cascade classifier files
│   ├── haarcascade_frontalface_alt.xml    # Face detection
│   ├── haarcascade_lefteye_2splits.xml    # Left eye detection
│   └── haarcascade_righteye_2splits.xml   # Right eye detection
│
└── README.md                # This file
```

## System Requirements
- Python 3.6+
- OpenCV
- Keras with TensorFlow backend
- Pygame
- NumPy
- Matplotlib

## Installation
1. Clone this repository:
   ```
   git clone https://github.com/ngocson/drowsiness_detection.git
   cd drowsiness_detection
   ```

2. Install required packages:
   ```
   pip install opencv-python tensorflow keras pygame numpy matplotlib
   ```

## Usage
1. Run the drowsiness detection system:
   ```
   python drowsinessdetection.py
   ```

2. Position yourself in front of the camera. The system will detect your face and eyes.

3. The system monitors for signs of drowsiness:
   - When eyes remain closed for too long, the "drowsiness score" increases
   - When the score exceeds a threshold (15), an audio alarm will sound
   - A red border appears on the screen to alert the user

4. Press 'q' to exit the application.

## How It Works
1. **Face and Eye Detection**: Uses Haar cascade classifiers to detect the face and both eyes in each frame.
2. **Eye State Classification**: A CNN model classifies the detected eyes as either "Open" or "Closed".
3. **Drowsiness Detection**: When both eyes are detected as closed for an extended period, the system determines the user is drowsy.
4. **Alert System**: Plays an alarm sound and displays visual alerts when drowsiness is detected.

## Model Training
The model.py script allows training the CNN model for eye state classification:
1. Prepare a dataset with "Open" and "Closed" eye images in the data/train and data/valid directories
2. Run `python model.py` to train the model
3. The trained model will be saved in the models directory

## Developer
Phạm Lê Ngọc Sơn

## License
This project is for educational and personal use.
