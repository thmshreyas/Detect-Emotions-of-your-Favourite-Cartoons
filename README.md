
# Detect Emotions of Your Favourite Cartoons

A deep learning project to detect and classify the emotions of cartoon characters from video frames using transfer learning and convolutional neural networks.

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Authors](#authors)
- [License](#license)

---

## About

**Detect Emotions of Your Favourite Cartoons** is a project that leverages deep learning to recognize and classify the emotions of cartoon characters from video frames. Using transfer learning with MobileNet, the model is trained to detect five emotion classes: `happy`, `surprised`, `angry`, `sad`, and `unknown`. The workflow includes frame extraction, data preparation, model training, and prediction output.

---

## Features

- **Cartoon Face Emotion Recognition:**  
  Classifies cartoon character faces into five emotion categories.
- **Transfer Learning:**  
  Utilizes MobileNet pre-trained on ImageNet for efficient feature extraction.
- **Custom Metrics:**  
  Implements F1-score, precision, and recall for robust model evaluation.
- **CSV Output:**  
  Generates a submission-ready CSV with predicted emotions for test frames.

---

## Getting Started

### Prerequisites

- Python 3.x
- TensorFlow / Keras
- OpenCV
- NumPy, pandas, matplotlib, seaborn

### Installation

1. Clone this repository:
   ```
   git clone https://github.com/thmshreyas/Detect-Emotions-of-your-Favourite-Cartoons.git
   cd Detect-Emotions-of-your-Favourite-Cartoons
   ```
2. Install dependencies:
   ```
   pip install 
   ```

---

## Usage

### 1. Frame Extraction

Extract frames from your cartoon video using OpenCV:
```
import cv2, math
videoFile = "Dataset/Train Tom and Jerry.mp4"
imageFolder = "Dataset/frameTrain"
cap = cv2.VideoCapture(videoFile)
frameRate = cap.get(5)
count = 0
while cap.isOpened():
    frameId = cap.get(1)
    ret, frame = cap.read()
    if not ret:
        break
    if frameId % math.floor(frameRate) == 0:
        filename = f"{imageFolder}/frame{count}.jpg"
        cv2.imwrite(filename, frame)
        count += 1
cap.release()
print("Done!")
```

### 2. Data Preparation

- Annotate frames and create `Train.csv` and `Test.csv` with `Frame_ID` and `Emotion` columns.
- Encode emotion labels and prepare features for model input.

### 3. Model Training

- Load MobileNet (with `include_top=False`).
- Add custom dense layers and softmax output.
- Compile and train the model with categorical crossentropy and custom F1 metric.

### 4. Prediction

- Preprocess test frames.
- Predict emotions and decode results.
- Save predictions to `Submission.csv`.

---

## Project Structure

```
.
├── Detect Emotions of your Favourite Cartoons.ipynb
├── Dataset/
│   ├── Train Tom and Jerry.mp4
│   ├── frameTrain/
│   ├── Train.csv
│   ├── Test.csv
│   └── frames/
│       ├── train_frames/
│       └── test_frames/
├── Submission.csv
├── requirements.txt
└── README.md
```

---

## Authors

- Samyak Sharma - 1DS22CS190
- Shashwat Kumar - 1DS22CS199
- Shaurya Katiyar - 1DS22CS200
- Shivansh Karan - 1DS22CS202
- Shreyas T H M - 1DS22CS208

---

## License

This project is licensed under the MIT License.

---

> For more details, see the full notebook: `Detect Emotions of your Favourite Cartoons.ipynb`

```
This format follows best practices for GitHub READMEs, including clear sections, concise descriptions, and usage instructions[1][2][4][5][6].
```

