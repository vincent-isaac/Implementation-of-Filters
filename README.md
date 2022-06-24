### EX NO : 06
### DATE  : 12.05.2022
# <p align="center">Implementation-of-Filters</p>

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules.

### Step2:
For performing smoothing operation on a image.

1. Average filter
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)

2. Weighted average filter
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)

3. Gaussian Blur
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)

4. Median filter
median=cv2.medianBlur(image2,13)


### Step3:
For performing sharpening on a image.
1. Laplacian Kernel
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)

2. Laplacian Operator
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
<br>
<br>
<br>

### Step4:
Display all the images with their respective filters.

## Program:
```python
### Developed By   : J Vincent isaac jeyaraj
### Register Number: 212220230060

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("H2.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

### 1. Smoothing Filters

i) Using Averaging Filter
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()

ii) Using Weighted Averaging Filter
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

iii) Using Gaussian Filter
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

iv) Using Median Filter
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Median Blur")
plt.axis("off")
plt.show()


### 2. Sharpening Filters
i) Using Laplacian Kernal
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

ii) Using Laplacian Operator
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
<br>
<br>

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter<br>
![output](https://user-images.githubusercontent.com/75234588/168142560-e397a6e9-55f5-4fef-890c-654f33dcbf3a.png)


ii) Using Weighted Averaging Filter<br>
![output1](https://user-images.githubusercontent.com/75234588/168142583-233c297d-f8f4-4b05-9a65-83b605867cdd.png)


iii) Using Gaussian Filter<br>
![output2](https://user-images.githubusercontent.com/75234588/168142611-684442d5-8c03-4c38-b1ef-59a4e8c02bfa.png)


iv) Using Median Filter<br>
![output3](https://user-images.githubusercontent.com/75234588/168142623-4f9c2091-223b-4d63-92d9-591914b0062e.png)

<br>
<br>
<br>

### 2. Sharpening Filters

i) Using Laplacian Kernal<br>
![output4](https://user-images.githubusercontent.com/75234588/168142655-69696088-61e0-4789-bc56-addaf19448ab.png)


ii) Using Laplacian Operator<br>
![output5](https://user-images.githubusercontent.com/75234588/168142674-a19a0282-0c68-410b-9b77-d298ddabd655.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
