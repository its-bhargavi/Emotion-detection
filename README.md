# Real-Time Emotion Detection Using Python

A computer vision project that detects faces through a webcam and classifies facial expressions into seven emotion categories using a pretrained Keras model.

## Overview

This project uses OpenCV for real-time video capture and face detection, and a trained deep learning model to predict the emotion category associated with each detected face. The predicted label is displayed on the webcam feed.

## Features

* Real-time webcam video capture
* Face detection using Haar Cascade
* Facial image preprocessing using grayscale conversion and resizing
* Emotion classification using a trained Keras model
* Seven emotion categories: Angry, Disgust, Fear, Happy, Sad, Surprise, and Neutral
* Live visualization of detected faces and predicted labels

## Tech Stack

* **Python** — application logic
* **OpenCV** — webcam access, image processing, and face detection
* **Keras / TensorFlow** — loading and running the trained model
* **NumPy** — numerical operations and image-array processing

## Project Structure

```text
EmotionDetectorProject/
├── main.py
├── emotion_model.hdf5
├── haarcascade_frontalface_default.xml
├── requirements.txt
├── .gitignore
└── README.md
```

## How It Works

1. **Load the model:** The application loads the trained emotion classification model and Haar Cascade face detector.
2. **Capture video:** OpenCV accesses the webcam and continuously reads frames.
3. **Detect faces:** Each frame is converted to grayscale, and the Haar Cascade classifier identifies face regions.
4. **Preprocess the face:** Each detected face is cropped, resized to `64 × 64` pixels, normalized to the range `0–1`, and reshaped into the model's expected input format.
5. **Predict emotion:** The model generates prediction scores for seven emotion categories. NumPy's `argmax()` selects the category with the highest score.
6. **Display results:** A rectangle is drawn around the face, and the predicted category is displayed on the video feed.

## Installation and Setup

### Prerequisites

* Python 3.12 (used for the tested local setup)
* A working webcam
* Git

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/EmotionDetectorProject.git
cd EmotionDetectorProject
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run the application

```bash
python main.py
```

Allow webcam access if prompted. The application will display the webcam feed with detected faces and predicted emotion labels.

Press **Q** while the webcam window is active to exit.

## Key Implementation Details

* **Haar Cascade:** Used for face detection through the XML classifier file.
* **Image normalization:** Dividing pixel values by `255.0` scales them to the `0–1` range.
* **Model inference:** `model.predict(roi)` generates the emotion prediction scores.
* **Class selection:** `np.argmax(prediction)` returns the index of the highest-scoring emotion category.

## Limitations

* Predictions depend on lighting, camera quality, face position, and model performance.
* Only faces detected by the classifier are processed.
* The application requires a working webcam.
* Facial-expression classifications do not reliably establish a person's actual emotional state.
* The current implementation processes frames locally and does not include a web interface, database, or real-time cloud service.

## Future Improvements

* Add confidence scores for predictions.
* Improve robustness under different lighting conditions.
* Add a graphical user interface.
* Evaluate model performance on a labeled test dataset.
* Optimize inference for better real-time performance.

## Disclaimer

This project is intended for educational and demonstration purposes. Emotion predictions are estimates based on facial appearance and should not be treated as definitive assessments of a person's feelings or mental state.

## Author

**Bhargavi Verma**

GitHub: https://github.com/its-bhargavi

