# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
#### Step1:Load the necessary packages.
#### Step2:Read the Image and convert to grayscale.
#### Step3:Use Global thresholding to segment the image.
#### Step4:Use Adaptive thresholding to segment the image.
#### Step5:Use Otsu's method to segment the image and display the results.

## Program
### Developed By : CHAITANYA P S 
### Register Number : 212222230024
```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
```
```python
# Read the Image and convert to grayscale

image = cv2.imread('dog.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('dog.jpeg',0)
```
```python
# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
```python
# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
```python
# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
```python
# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image

<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/e380762b-2d99-4c13-a1ce-148c9b8a0d23" width=50%>

### Global Thresholding

<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/bacd1106-bb69-4aae-b988-23b161a57fc3" width=50%>
<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/24617150-abe0-4a46-8afb-80eec9efa271" width=50%>
<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/a0bc5c30-8a3f-4ce9-8d76-f5e452e5dd72" width=50%>
<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/c5068b3a-dac7-4c19-8f2a-1c4caa140139" width=50%>
<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/4a6f7b6c-ea63-4143-b5ee-dbc07bc853ea" width=50%>


### Adaptive Thresholding

<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/d5859752-96fa-4c73-81f3-864b1d2a7dba" width=50%>
<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/e1c81e41-51d5-4ce8-bc57-b078949524a9" width=50%>

### Optimum Global Thesholding using Otsu's Method

<img src="https://github.com/chaitanya18c/Thresholdingg/assets/119392724/8ece06ce-2e2c-4c43-9c5b-d484222d406e" width=50%>

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
