## 📁 Dataset Access

To run the image recognition model, you'll need the dataset stored on Google Drive.

🔗 [Download the dataset](https://drive.google.com/drive/folders/1T66tlNMRkInr8mQoce6KJIUOwSvBn7Fj?usp=sharing)

After downloading, place the files in the following structure:
├── train/ 
├── val/ 
└── test/
🔗 [Example](https://drive.google.com/drive/folders/16NLBRQlF_2thtIvkpcR9V3_XcIjToZFE?usp=sharing)

Make sure your Google Drive is mounted if you're using Google Colab.

Source: https://www.kaggle.com/datasets/mdwaquarazam/agricultural-crops-image-classification/data

# Agricultural Crop Image Classification

This project implements an image classification model using a pre-trained ResNet50 model with transfer learning to classify crops. The model is trained on a custom dataset of agricultural crop images, utilizing data augmentation and early stopping to enhance performance and prevent overfitting.

## Features:

*   Leverages transfer learning with ResNet50 for efficient training.
*   Includes data augmentation techniques to enhance model robustness.
*   Implements early stopping to mitigate overfitting.
*   Provides a function for making predictions on new images.

## Model Architecture:

The model consists of the following layers:

1.  **ResNet50 Base Model:** Pre-trained on ImageNet, with the top classification layer removed. The base model's weights are frozen during initial training.
2.  **Global Average Pooling 2D:** Reduces the spatial dimensions of the output from the base model.
3.  **Dense Layer (256 units):** A fully connected layer with ReLU activation.
4.  **Dropout Layer (0.5 dropout rate):** Helps to prevent overfitting by randomly setting a fraction of input units to zero during training.
5.  **Dense Layer (number of classes units):** The final output layer with softmax activation for multi-class classification.

## Training:
The model is compiled with the Adam optimizer and categorical crossentropy loss. Early stopping is used to monitor validation loss and stop training when it no longer improves.

## Evaluation and Prediction:
The model's performance is evaluated on the test set. A function is provided to make predictions on new, unseen images.
