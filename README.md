# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>Import libraries and read the saved images using cv2.imread().
</br> 

### Step2
</br>Convert the saved BGR image to RGB using cvtColor().
</br> 

### Step3
</br>By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.
</br> 

### Step4
</br>Apply the filters using cv2.filter2D() for each respective filters.
</br> 

### Step5
</br>Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
</br> 

## Program:
### Developed By   : JANANI R
### Register Number: 212221230039
</br>
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("pooh.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
```
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")
```
ii) Using Laplacian Operator
```Python
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
</br>![smooth1](https://user-images.githubusercontent.com/94288340/235211563-68127094-5093-440b-96c6-cbd8f4c9c586.png)

</br>
</br>
</br>
</br>

ii) Using Weighted Averaging Filter
</br>![smooth2](https://user-images.githubusercontent.com/94288340/235211588-37f5fa66-8410-4073-9e3e-ccc9b482f041.png)

</br>
</br>
</br>
</br>

iii) Using Gaussian Filter
</br>![smooth3](https://user-images.githubusercontent.com/94288340/235211618-7894bd80-25fc-462b-a12a-8ef5a53e7039.png)

</br>
</br>
</br>
</br>

iv) Using Median Filter
</br>![smooth4](https://user-images.githubusercontent.com/94288340/235211662-b3585ff6-7b21-44a8-9c43-93416faf58e6.png)

</br>
</br>
</br>
</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>![sharp1](https://user-images.githubusercontent.com/94288340/235211703-1ce25431-8bf6-4a5d-9deb-3f51762246cc.png)

</br>
</br>
</br>
</br>

ii) Using Laplacian Operator
</br>![sharp2](https://user-images.githubusercontent.com/94288340/235211730-a1789d23-0cd1-47c3-93a5-63d6a57cc183.png)

</br>
</br>
</br>
</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
