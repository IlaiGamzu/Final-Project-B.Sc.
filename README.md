# Image Reconstruction Through a Scattering Medium using an Encoder - Decoder Network

## Overview

This project presents an end-to-end deep learning system for
reconstructing blurred images captured through a scattering medium.

The motivation behind this work is to investigate safer optical imaging
techniques that could eventually complement conventional X-ray imaging.
While Near-Infrared (NIR) imaging is significantly safer than X-rays,
its limited penetration and strong scattering produce highly blurred
images. This project explores whether a convolutional Encoder--Decoder
neural network can recover the original image from these degraded
observations.

> **Note**
>
> The practical implementation presented in this project does **not**
> use an actual NIR imaging system. Instead, it simulates optical
> degradation using a visible-light Basler camera and a scattering
> medium to validate the reconstruction approach.

------------------------------------------------------------------------

## Project Pipeline

``` text
MNIST Dataset
      │
      ▼
Image Preprocessing
      │
      ▼
Display on Waveshare E-Paper
      │
      ▼
Scattering Medium
      │
      ▼
Basler Camera Acquisition
      │
      ▼
Image Cropping & Dataset Creation
      │
      ▼
Encoder–Decoder CNN
      │
      ▼
Reconstructed Image
```

------------------------------------------------------------------------

## Features

-   Convolutional Encoder--Decoder architecture
-   Skip Connections
-   Convolution + MaxPooling blocks
-   Batch Normalization
-   ReLU activation
-   Sigmoid output activation
-   Mean Squared Error (MSE) loss
-   Adam optimizer
-   Train / Validation / Test split
-   Simulation and real hardware validation

------------------------------------------------------------------------

## Hardware Setup

-   Basler acA1440-220um Camera
-   Raspberry Pi 4B
-   Waveshare E-Paper Display
-   LED illumination
-   USB 3.0 Hub
-   Custom 3D-printed mount
-   Scattering medium

------------------------------------------------------------------------

## Software Stack

-   Python
-   TensorFlow / Keras
-   OpenCV
-   NumPy
-   Raspberry Pi OS
-   Basler Pylon SDK
-   UART Communication
-   PIL

------------------------------------------------------------------------

## Dataset

The project uses the MNIST handwritten digits dataset.

Pipeline:

1.  Resize images
2.  Convert to BMP
3.  Display on the Waveshare display
4.  Capture using the Basler camera
5.  Crop captured images
6.  Create paired datasets (Original / Blurred)

------------------------------------------------------------------------

## Neural Network

### Encoder

-   Convolution
-   ReLU
-   Batch Normalization
-   MaxPooling

### Decoder

-   Upsampling
-   Convolution
-   Skip Connections
-   Sigmoid output

------------------------------------------------------------------------

## Training

**Loss Function**

-   Mean Squared Error (MSE)

**Optimizer**

-   Adam

**Activation Functions**

-   ReLU
-   Sigmoid

**Dataset Split**

-   70% Training
-   10% Validation
-   20% Testing

------------------------------------------------------------------------

## Experimental Validation

### Simulation

Synthetic blur was generated from the MNIST dataset to validate the
reconstruction model.

### Real Optical System

The complete optical setup consists of:

-   Waveshare display
-   Scattering medium
-   Basler camera
-   Raspberry Pi

Captured images were used to train and evaluate the neural network.

------------------------------------------------------------------------

## Results

The proposed system successfully reconstructed blurred images generated
by the scattering medium.

Training and validation curves demonstrated stable convergence without
significant overfitting, validating the feasibility of combining optical
acquisition with deep learning for image restoration.

------------------------------------------------------------------------

## Future Work

-   Real Near-Infrared (NIR) imaging
-   Biomedical imaging
-   Early tumor detection
-   Internal tissue visualization
-   Larger datasets
-   Improved neural network architectures
-   SSIM / Perceptual Loss
-   Real-time inference


------------------------------------------------------------------------

## Authors

**Ilai Gam Zu Letova**

Electrical & Computer Engineer


**Oriya Avdar**

Electrical & Computer Engineer

------------------------------------------------------------------------

## Supervisor

**Dr. Yossi Danan**

Department of Electrical and Electronics Engineering

Azrieli College of Engineering Jerusalem

------------------------------------------------------------------------

## License

This repository is released for academic and research purposes.
