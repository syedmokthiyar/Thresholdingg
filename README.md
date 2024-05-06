# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.


## Program
Developed By : Syed Mokthiyar S.M
Register Number : 212222230156

# Load the necessary packages
```python

import numpy as np
import matplotlib.pyplot as plt
import cv2
```


# Read the Image and convert to grayscale
```python
image = cv2.imread('sam.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('sam.jpeg',0)
```


# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

```

# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
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
![Screenshot 2024-05-06 231125](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/0b2ba9a1-660e-4696-8f01-de6db34ad6d8)
![Screenshot 2024-05-06 231518](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/56b6deb3-6302-44ba-b79b-dfae99a9a025)
![Screenshot 2024-05-06 231540](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/344d0ca5-e58e-4407-8111-285f703f9c51)


### Global Thresholding
![Screenshot 2024-05-06 231453](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/9f5c1497-18d7-4504-a005-c9c755bf7c73)


### Adaptive Thresholding
![Screenshot 2024-05-06 231345](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/4bcab8d1-51de-4040-862e-15c857649b4e)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-05-06 231243](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/93cfd3df-2a16-46b9-8cbc-003c51892027)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
