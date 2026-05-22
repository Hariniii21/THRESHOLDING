# THRESHOLDING

# EXP-8-THRESHOLDING
## Developed By: HARINI S
## Reg No.: 212223240048
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale
### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.
## Program
NAME : Harini

REG NO : 212223240048
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('thres.png') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")
plt.axis('off')


_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

plt.tight_layout()
plt.show()
```
## Output
### Original Image
<img width="279" height="238" alt="image" src="https://github.com/user-attachments/assets/5b7ba630-fefc-44b4-a025-89b5d6bfb7b7" />

### Global Thresholding
<img width="368" height="242" alt="image" src="https://github.com/user-attachments/assets/81ccd75e-4a3d-4bad-9347-101b1d1dcd1e" />

### Adaptive thresholding
<img width="454" height="243" alt="image" src="https://github.com/user-attachments/assets/825f5402-65cc-4e74-af4b-263793d21b46" />

### Otsu Method

<img width="677" height="271" alt="image" src="https://github.com/user-attachments/assets/64b78835-fc8e-46dc-b9f6-54bbdd769aed" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
