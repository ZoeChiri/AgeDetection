# AgeDetection

## Overview
AgeDetection is a deep learning project aimed at accurately predicting the age of individuals from images. This project serves as a practice for implementing various deep learning techniques and models for age estimation.

## Features
- Utilizes convolutional neural networks (CNNs) for age prediction.
- Supports training on custom datasets.
- Allows camera useage to upload your own photo.
- Pre-trained models available for quick testing.


## 1. Pretrained data 

### Code Explanation
- The provided code includes the following steps: Image Import and Resizing

- The pre-trained age detection model is loaded using Caffe model files (age_deploy.prototxt and age_net.caffemodel).

- Face Detection Dlib’s face detector is used to locate faces within the image. The image is converted to black and white, then tries to detect a face.

- Age Prediction
For each detected face, the code processes the image and uses the age detection model to predict the age group.
- Display Results
The results are displayed with bounding boxes around detected faces and the predicted age labels.

Pretrained data
Input:


![jenna_ortega](https://github.com/user-attachments/assets/a2214435-b231-492c-a359-bfb5c76c17e6)

Output:


![jenna_ortega_age](https://github.com/user-attachments/assets/46f99056-276e-439c-8fbc-7cd9f5e48601)

This is probably why Jenna Ortega is casted so young. The model isn't entirely accurate, but improving it will be in later steps. 

## 2. Capturing Images 

This section of the code allows users to capture an image directly from their webcam while using Google Colab. The `take_photo` function utilizes JavaScript to interact with the browser’s media devices, enabling real-time video streaming and image capturing.

The `take_photo` function does the following:

### Code Explanation

1. **Setup for Webcam Access**: It prompts the user for permission to access their webcam and starts a video stream.
2. **User Interface**: A button labeled "Capture" is displayed alongside the video feed, allowing the user to take a photo.
3. **Mirrored Video**: The video is mirrored to provide a more natural viewing experience for the user.
4. **Image Capture**: Upon clicking the "Capture" button, the current frame from the video stream is drawn onto a canvas element.
5. **Image Processing**: The captured image is converted to a base64-encoded string, which is then decoded into binary format.
6. **Saving the Image**: The resulting image is saved as a JPEG file with a specified filename.

Camera works and shows "Capture Image"

![IMG_7263](https://github.com/user-attachments/assets/b90d5ca8-7959-4379-8432-9194ef29dc2f)


Output:

![IMG_7262](https://github.com/user-attachments/assets/4e62e6a8-3cc0-4cb6-9226-6174656d9365)

note: I did change poses oops...

The model is doing a bit better here, I can't expect it to be 100% accurate since this isn't a regression model where we have the actual age outputs. That would produce better results, but I want to make this model on looks alone. I am not in the 25-30 demographic, but it is getting closer to my actual age. 

## 3. Model Improvements
Using DeepFace we get the output for the Jenna Ortega image above "Predicted Age: 25"
Which is way closer than what we got using Caffe model.
