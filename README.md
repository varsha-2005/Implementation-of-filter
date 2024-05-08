# Implementation of filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:

Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:

 ### Developed By:Varsha G
 ### Register Number:212222230166

### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
#### ii) Using Weighted Averaging Filter
```python
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
#### iii) Using Gaussian Filter
```python
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

#### iv) Using Median Filter
```python
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
#### i) Using Laplacian Kernel
```python
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
#### ii) Using Laplacian Operator
```python
image1 = cv2.imread('peacock.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
### 1. Smoothing Filters

#### i) Using Averaging Filter

![51](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/4c8323fb-6d9d-426f-8303-14002c27524e)


#### ii) Using Weighted Averaging Filter

![52](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/890b1659-e9d4-4ca6-b492-b685ab07caf3)


#### iii) Using Gaussian Filter

![53](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/0cdb7f52-09b5-4270-bf81-a96947aa6153)


#### iv) Using Median Filter

![54](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/4092d776-9e1d-4f5c-8971-c8944bdf3229)

### 2. Sharpening Filters

#### i) Using Laplacian Kernel

![55](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/943bcb30-0aec-491a-9e35-d93ce8a8c29d)

#### ii) Using Laplacian Operator

![56](https://github.com/JananiSoundararajan/Implementation-of-filter/assets/119477549/7ba645bd-b25e-4a7d-ac6b-3dff7c492068)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
