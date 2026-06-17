# Deep-Fake-Detection-model
The Deep Fake Recognition System is a software-based solution that uses Artificial Intelligence and Deep Learning techniques to analyze images and videos. The main aim of this system is to identify fake content by studying facial features, expressions, texture, lighting, and motion patterns.In this project, a Convolutional Neural Network is used.
# Deepfake Video Detection

A computer vision and deep learning project designed to classify videos as **Real** or **Fake**. This project focuses on parsing raw video data, extracting structural image frames using OpenCV, and utilizing a neural network architecture to detect visual artifacts and digital manipulations.

The core pipeline and experimental workflows are documented inside the `Deep_fake_video_detection.ipynb` notebook.

## Project Architecture & Pipeline

The pipeline follows a standard machine learning workflow for video classification, executed in the following sequence:

1. **Data Acquisition:** Downloads and extracts targeted real/fake video datasets (such as the FaceForensics++ or DFDC subsets available on Kaggle).
2. **Video Preprocessing:** Due to temporal redundancy, videos are not passed directly into the model. Instead, frames are sampled at sequential intervals using OpenCV.
3. **Data Augmentation & Scaling:** Extracted frames are converted to RGB color space, resized to standard dimensions (e.g., `224x224`), and normalized.
4. **Model Training:** Utilizes a Convolutional Neural Network (CNN) backbone—often paired with Recurrent layers (LSTM) or Dense classifier heads—to output binary classification probabilities.
5. **Evaluation:** Evaluates validation and testing splits using metrics like Accuracy, Loss curves, and Confusion Matrices.

---

## Directory Structure

```text
deepfake-detection/
│
├── Deep_fake_video_detection.ipynb  # Main development and training notebook
├── datasets/                        # Local directory for raw train/test video clips
├── extracted_frames/                # Directory for processed image frames (cache)
