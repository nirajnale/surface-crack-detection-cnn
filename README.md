# 🏗️ Surface Crack Detection using Convolutional Neural Networks (CNN)

> An end-to-end Computer Vision application for automated surface crack detection using Convolutional Neural Networks (CNNs) built with TensorFlow and Keras. The project demonstrates a complete deep learning workflow including dataset preparation, preprocessing, model training, evaluation, visualization, and single-image inference.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange)
![Keras](https://img.shields.io/badge/Keras-CNN-red)
![Computer Vision](https://img.shields.io/badge/Computer-Vision-success)
![Image Classification](https://img.shields.io/badge/Image-Classification-blueviolet)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 Project Overview

Surface inspection is an important task in industrial quality control, where manual inspection can be time-consuming and prone to human error. This project implements a Convolutional Neural Network (CNN) to automatically classify surface images into **Crack** and **No Crack** categories.

The implementation follows an end-to-end machine learning pipeline, beginning with dataset organization and preprocessing, followed by model training, evaluation on unseen data, visualization of training metrics, and single-image prediction.

---

# ❓ Problem Statement

Manual inspection of concrete or industrial surfaces is labor-intensive and may lead to inconsistent results. The objective of this project is to automate crack detection using image classification with a CNN-based approach.

---

# 🎯 Objectives

- Build an end-to-end computer vision pipeline.
- Automate binary crack classification.
- Apply CNNs for image classification.
- Demonstrate reproducible training and evaluation workflows.
- Visualize model performance.
- Perform inference on unseen images.

---

# ✨ Features

- Automated dataset splitting (Train / Validation / Test)
- Image preprocessing
- Data augmentation
- CNN-based binary classifier
- Batch Normalization
- Dropout regularization
- Early Stopping
- Model Checkpointing
- Learning Rate Scheduling
- Accuracy & Loss visualization
- Confusion Matrix
- Classification Report
- Saved trained models
- Single image prediction

---

# 🏗 High-Level Architecture

```text
Original Dataset
        │
        ▼
Dataset Validation
        │
        ▼
Train / Validation / Test Split
        │
        ▼
Image Preprocessing
        │
        ▼
Data Augmentation
        │
        ▼
CNN Model
        │
        ▼
Training
        │
        ▼
Validation
        │
        ▼
Testing
        │
        ▼
Model Saving
        │
        ▼
Single Image Prediction
```

---

# 📂 Dataset Pipeline

The project expects the original dataset to be organized as:

```text
CrackDataset/
├── Positive/
└── Negative/
```

During execution, the dataset is automatically reorganized into:

```text
Processed_CrackDataset/

├── train/
│   ├── Crack/
│   └── NoCrack/
│
├── validation/
│   ├── Crack/
│   └── NoCrack/
│
└── test/
    ├── Crack/
    └── NoCrack/
```

Dataset splitting strategy implemented:

- Training: **70%**
- Validation: **15%**
- Testing: **15%**

---

# 🖼 Data Preprocessing

The preprocessing pipeline includes:

- Image resizing (128 × 128)
- Pixel normalization (`1/255`)
- Directory-based dataset loading
- Binary class labeling

These steps ensure consistent input dimensions and stable model training.

---

# 🔄 Data Augmentation

Training images undergo online augmentation using `ImageDataGenerator`.

Implemented augmentations:

- Rotation
- Zoom
- Horizontal Flip
- Width Shift
- Height Shift

Validation and testing datasets are only normalized to preserve unbiased evaluation.

---

# 🧠 CNN Architecture

The implemented CNN consists of:

| Layer | Configuration |
|--------|--------------|
| Conv2D | 32 Filters + ReLU |
| BatchNormalization | ✓ |
| MaxPooling | 2×2 |
| Conv2D | 64 Filters + ReLU |
| BatchNormalization | ✓ |
| MaxPooling | 2×2 |
| Conv2D | 128 Filters + ReLU |
| BatchNormalization | ✓ |
| MaxPooling | 2×2 |
| Conv2D | 256 Filters + ReLU |
| BatchNormalization | ✓ |
| MaxPooling | 2×2 |
| Flatten | ✓ |
| Dense | 256 + ReLU |
| Dropout | 0.5 |
| Dense | 128 + ReLU |
| Dropout | 0.3 |
| Output | Sigmoid |

Loss Function:

- Binary Cross Entropy

Optimizer:

- Adam

Evaluation Metric:

- Accuracy

---

# 🚀 Training Workflow

The training pipeline includes:

- Dataset loading
- Batch generation
- CNN training
- Validation after every epoch
- Automatic learning rate reduction
- Early stopping
- Best model checkpointing

Callbacks implemented:

- EarlyStopping
- ModelCheckpoint
- ReduceLROnPlateau

These improve training stability and reduce overfitting.

---

# 📊 Validation & Evaluation

The project evaluates the trained model using:

- Test Loss
- Test Accuracy
- Confusion Matrix
- Classification Report

Evaluation is performed on an unseen test dataset separated before training.

---

# 🔍 Inference Pipeline

For inference, the project:

1. Loads an image.
2. Resizes it to the expected input size.
3. Converts it into an array.
4. Normalizes pixel values.
5. Performs CNN prediction.
6. Converts prediction probability into a class label.
7. Displays the prediction along with the input image.

---

# 🔄 Prediction Workflow

```text
Input Image
      │
      ▼
Resize
      │
      ▼
Normalization
      │
      ▼
Tensor Conversion
      │
      ▼
CNN Prediction
      │
      ▼
Probability Threshold
      │
      ▼
Crack / No Crack
```

---

# 📁 Project Structure

```text
surface-crack-detection-cnn/

├── src/
│   └── surface_crack_detection_cnn.py
│
├── README.md
│
├── CrackDataset/
│
├── Processed_CrackDataset/
│
├── Best_Crack_Detection_Model.keras
│
└── Final_Marvellous_Crack_Detection_Model.keras
```

---

# 🛠 Technologies Used

### Programming

- Python

### Deep Learning

- TensorFlow
- Keras

### Computer Vision

- CNN
- ImageDataGenerator

### Data Processing

- NumPy

### Visualization

- Matplotlib

### Evaluation

- Scikit-learn

---

# 👁️ Computer Vision Concepts Demonstrated

- Image Classification
- CNN Feature Extraction
- Convolution Layers
- Max Pooling
- Batch Normalization
- Binary Classification
- Image Preprocessing
- Data Augmentation
- Model Inference

---

# 🤖 Machine Learning Concepts Demonstrated

- Binary Classification
- Train / Validation / Test Split
- Model Evaluation
- Hyperparameter Configuration
- Early Stopping
- Learning Rate Scheduling
- Regularization using Dropout
- Performance Visualization

---

# 💻 Engineering Concepts Demonstrated

- Modular pipeline organization
- Automated dataset preparation
- Reproducible random seeds
- Model checkpointing
- Training callbacks
- Visualization of learning curves
- Model persistence
- End-to-end prediction workflow

---

# 📈 Results

The implementation generates:

- Training Accuracy Curve
- Validation Accuracy Curve
- Training Loss Curve
- Validation Loss Curve
- Test Accuracy
- Test Loss
- Confusion Matrix
- Classification Report

> This README intentionally does **not** report numerical accuracy or performance values because they depend on the dataset and training run.

---

# 🖼 Sample Predictions

The implementation supports single-image prediction and displays:

- Input image
- Prediction probability
- Final predicted class

---

# ⚙️ Installation

```bash
git clone https://github.com/yourusername/surface-crack-detection-cnn.git

cd surface-crack-detection-cnn

pip install tensorflow keras matplotlib numpy scikit-learn
```

---

# 🚀 Training

Run:

```bash
python src/surface_crack_detection_cnn.py
```

Training automatically performs:

- Dataset validation
- Dataset splitting
- Data augmentation
- CNN training
- Validation
- Model checkpointing
- Final model saving

---

# 📊 Evaluation

After training, the script automatically computes:

- Test Accuracy
- Test Loss
- Confusion Matrix
- Classification Report

---

# 🔍 Inference

The implementation includes single-image inference for predicting whether an image contains a crack or not.

---

# 🚀 Future Improvements

Potential enhancements include:

- Configuration files
- Transfer Learning (ResNet/EfficientNet/MobileNet)
- Grad-CAM visualizations
- TensorBoard integration
- Docker support
- Model serving API
- ONNX export
- Unit tests
- Requirements file
- Project modularization into separate training and inference scripts

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Niraj Vijaysinh Nale**

B.Tech Robotics & Automation  
MIT World Peace University, Pune

Interested in Artificial Intelligence, Computer Vision, Deep Learning, Machine Learning, and Software Engineering.

---

⭐ If you found this project useful, consider giving it a star.
