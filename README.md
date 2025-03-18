# Automated Medical Image Diagnostics using QML

dataset can be found [here](https://drive.google.com/drive/folders/1kFSl8acOOQLJwG3v9Sdx2Q-TKpkA_U8b?usp=drive_link):

This project integrates quantum processing demonstrating the potential of quantum convolution in image classification tasks. The readme file could further discuss the implications of combining quantum and classical approaches and interpret the training results.

## Problem Statement

The mission is to delve into the unique convergence of quantum computing and image analysis. Specifically, aim is to implement a model classifying face image data set to predict Autisim disorder  And to unravel the mysteries of QCNN architecture and its application in classifying images, while keeping a keen focus on the medical dataset. Furthermore, we endeavor to draw comparisons between the QCNN and its classical counterpart, the Convolution Neural Network (CNN).

## Procedure

1. **Initialization and Configuration:**
   - The code starts by importing necessary libraries, including PennyLane for quantum computing, TensorFlow for classical deep learning, and Matplotlib for visualization.
   - Parameters such as the number of optimization epochs (`n_epochs`), the number of random layers in the quantum circuit (`n_layers`), and dataset sizes are set.

2. **Dataset Loading and Preprocessing:**
   - Images and labels are collected from the "consolidated" dataset folder, where images are categorized into "Autistic" and "Non_Autistic" subfolders.
   - Labels are encoded with indices for autistic and non-autistic classes.
   - Image preprocessing involves resizing, normalization, and adding an extra dimension for convolution channels. The dataset is then split into training and testing sets using `train_test_split` from scikit-learn.
  
![Framework](./output.png)

3. **Quantum Circuit Definition (`circuit`):**
   - A quantum device with 4 qubits is created using PennyLane.
   - The quantum circuit `circuit` is defined as a QNode (quantum node) using PennyLane's automatic differentiation interface. It consists of encoding classical input values, applying random quantum layers, and measuring classical output values.

4. **Quantum Convolution (`quanv`):**
   - The function `quanv` convolves the input image with multiple applications of the same quantum circuit. It processes squared 2x2 regions of the image using the quantum circuit, producing a quantum-processed image with multiple channels.

5. **Quantum Pre-processing of Images:**
   - Training and test images are quantum pre-processed using the `quanv` function. The quantum circuit is applied to 2x2 regions of each image, and the results are stored in `q_train_images` and `q_test_images`.

6. **Saving Pre-processed Images:**
   - The quantum pre-processed images are saved in a specified directory.

7. **Visualization:**
   - A visualization is created to show original and quantum-processed images side by side. The first row displays original images, and subsequent rows display the output channels of the quantum-processed images.


