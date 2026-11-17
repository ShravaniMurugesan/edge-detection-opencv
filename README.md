# EDGE-DETECTION
## NAME : SHRAVANI M
## REG NO : 212224230263
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.


## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sunflower.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)

sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  # Sobel X
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  # Sobel Y
sobel_combined = cv2.magnitude(sobelx, sobely) 

plt.figure(figsize = (12, 16))
plt.subplot(321); plt.axis('on'); plt.imshow(image[:,:,::-1]); plt.title('Original')
plt.subplot(322); plt.axis('on'); plt.imshow(gray_image, cmap='gray');plt.title('Grayscale') 
plt.subplot(323); plt.axis('on'); plt.imshow(sobelx);plt.title('Sobel-X Edge Map')
plt.subplot(324); plt.axis('on'); plt.imshow(sobely);plt.title('Sobel-Y Edge Map')

plt.figure(figsize = (12, 16))
plt.axis('off'); plt.imshow(sobel_combined, cmap='gray' ); plt.title('sobel_combined ')

```
## Output:
### SOBEL EDGE DETECTOR & LAPLACIAN EDGE DETECTOR:

<img width="990" height="465" alt="image" src="https://github.com/user-attachments/assets/802d8e9b-6b50-4cea-92df-f12b8d1d0d6f" />



### CANNY EDGE DETECTOR

<img width="853" height="437" alt="image" src="https://github.com/user-attachments/assets/880e849b-fc4a-4e5d-9b52-b9fd559a384d" />

<img width="592" height="800" alt="image" src="https://github.com/user-attachments/assets/96eade6b-0274-4064-89bb-761cc0ea2e97" />



## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
