## Histogram-Equalization-Using-OpenCV
### Name: SUBHASH V
### Register Number: 212224240163

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By: SUBHASH V**

**Register Number: 212224240163**

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="447" height="542" alt="image" src="https://github.com/user-attachments/assets/7d014588-86b9-44ad-9b54-7a11f0b7e45f" />


### Input Grayscale Image Range
<img width="710" height="542" alt="image" src="https://github.com/user-attachments/assets/c7f70576-e2f1-4050-88f1-54fe5851af62" />


### Input Grayscale Image Equalized Histogram
<img width="722" height="575" alt="image" src="https://github.com/user-attachments/assets/50ead1d2-8efc-446d-a105-536a63d1013e" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="450" height="542" alt="image" src="https://github.com/user-attachments/assets/51e534db-0408-4a6d-a026-56e089156a14" />


### Equalized Image

<img width="445" height="535" alt="image" src="https://github.com/user-attachments/assets/f53ad655-c724-404a-be83-ffc8cd3a72e1" />


### Equalized Histogram

<img width="713" height="530" alt="image" src="https://github.com/user-attachments/assets/be13c777-ecdc-420b-ba47-28f8dc07771e" />


### Final Output of Original Image and Equalized 

<img width="888" height="325" alt="image" src="https://github.com/user-attachments/assets/75d270cd-824a-4401-95c7-612cfbe397bf" />


### Final Output of Original Image and its Histogram Equalized

<img width="872" height="292" alt="image" src="https://github.com/user-attachments/assets/3073a84f-46c8-4304-ba29-1eb1196998cd" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
