# Metal Surface Defects Classification (CNN – 6 Classes)

This project focuses on classifying six types of metal surface defects using a Convolutional Neural Network (CNN).  
In real-world manufacturing environments, surface defect identification is still predominantly manual.  
This project automates defect classification, enabling faster quality control and improved reliability in industrial processes.

---

## Problem Statement

Hot-rolled steel strips often contain defects such as cracks, inclusions, roll marks, stains, etc.  
Manual visual inspection is:

- Slow  
- Prone to errors  
- Difficult to scale  

The goal of this project is to build an **AI-based automated defect classification system** that can accurately distinguish between six common defect types.

---

## Dataset Description

The dataset used is the **NEU Metal Surface Defects Database**, which contains **1,800 grayscale images** categorized into:

| Class | Description            | Samples |
|-------|-------------------------|---------|
| RS    | Rolled-in Scale         | 300     |
| Pa    | Patches                 | 300     |
| Cr    | Crazing                 | 300     |
| PS    | Pitted Surface          | 300     |
| In    | Inclusion               | 300     |
| Sc    | Scratches               | 300     |

## Dataset Split Used in This Project

- **Training:** 276 images per class  
- **Validation:** 12 images per class  
- **Testing:** 12 images per class  

All images were resized and normalized before training.

---

## CNN Model Architecture

A custom CNN was designed for this task.  
Below is the architecture summary:

| Layer (type)         | Output Shape        | Param #     |
|----------------------|---------------------|-------------|
| **conv2d_6**         | (None, 199, 199, 32) | 416         |
| **max_pooling2d_6**  | (None, 99, 99, 32)   | 0           |
| **conv2d_7**         | (None, 98, 98, 64)   | 8,256       |
| **max_pooling2d_7**  | (None, 49, 49, 64)   | 0           |
| **conv2d_8**         | (None, 48, 48, 128)  | 32,896      |
| **max_pooling2d_8**  | (None, 24, 24, 128)  | 0           |
| **flatten_2**        | (None, 73728)        | 0           |
| **dense_4**          | (None, 256)          | 18,874,624  |
| **dropout_2**        | (None, 256)          | 0           |
| **dense_5**          | (None, 6)            | 1,542       |

---

## **Model Parameters**
- **Total params:** 18,917,734  
- **Trainable params:** 18,917,734  
- **Non-trainable params:** 0  


 
---

## Training Details

- **Optimizer:** rmsprop  
- **Loss:** Categorical Crossentropy  
- **Metrics:** Accuracy
- **Batch Size:** 32
- **Epochs:** 20  
- **Image Size:** 200*200

---

## Results

- **Training Accuracy:** 81.40%  
- **Validation Accuracy:** 63.89%  
- **Test Accuracy:** 75.60%  

![Classification Result](images_for_readme/Classification_Results.png)







