# EXP 08
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step 2:
Read the Image and convert to grayscale.
### Step 3:
Use Global thresholding to segment the image.
### Step 4:
Use Adaptive thresholding to segment the image.
### Step 5:
Use Otsu's method to segment the image.
### Step 6:
Display the results.

## Program
```
Developed by: HENRIPRASATH S
Register No: 212223230077
```
### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread("dodge.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dodge.jpg",0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
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

![Screenshot 2025-05-21 020116](https://github.com/user-attachments/assets/bfa72cf3-4fb9-4cab-9b6f-5f277f10743e)


### Global Thresholding

![Screenshot 2025-05-21 020148](https://github.com/user-attachments/assets/35a3189b-c265-475e-b456-5940e6ed7042)

![Screenshot 2025-05-21 020208](https://github.com/user-attachments/assets/3dbf2f85-218e-4e46-b2ef-d812afa9a177)

![Screenshot 2025-05-21 020223](https://github.com/user-attachments/assets/c56c8338-b177-485e-aa3f-6b63ab468e5e)


### Adaptive Thresholding

![Screenshot 2025-05-21 020246](https://github.com/user-attachments/assets/ca2a5639-b784-4f8e-b85a-7b720530d02c)


### Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-05-21 020300](https://github.com/user-attachments/assets/24a85fd8-9003-4d24-a6f5-bfa26ad339cf)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
