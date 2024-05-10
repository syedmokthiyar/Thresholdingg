# EX:08 THRESHOLDING
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
![Screenshot 2024-05-10 091404](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/006efc5c-bbc9-45fc-af01-d6b15c2f6ecb)
![Screenshot 2024-05-10 092302](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/d64b9cc9-c9ba-43d9-b9bf-aba41dc42e9d)


![Screenshot 2024-05-10 092348](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/a461a00e-0720-4909-81f9-1e4ae50bd8b4)


### Global Thresholding
![Screenshot 2024-05-10 092110](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/979cb58c-6bc9-4716-9951-701205923074)

### Adaptive Thresholding
![Screenshot 2024-05-10 091804](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/ab06e6ae-e8c1-4891-ab14-92267c9e531e)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-05-10 091722](https://github.com/syedmokthiyar/Thresholdingg/assets/118787294/8d077115-53ec-4b7e-95d3-15e675bca4f8)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
