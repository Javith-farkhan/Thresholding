# Thresholding-of-Images...

## Aim:

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:

Anaconda - Python 3.7,

OpenCV.

## Algorithm:

### Step 1:

Load the necessary packages requiured for the processing the threshold of the image.

### Step 2:

Read the Image using the cv2 instructions and convert it to a grayscale image.

### Step 3:

Apply global thresholding on the grayscale image and store the results in threshold variables. Use different thresholding methods to segment the image.

### Step 4:

Apply adaptive thresholding on the grayscale image and store the results in the variables th1 and th2. Use different adaptive thresholding methods to segment the immage. 

### Step 5:

Apply Otsu's method on the grayscale image and store the result in variable th3.

### Step 6:

Create a list titles containing the titles of each image and a list images containing the corresponding images.

### Step 7:

Loop through the images list to display each image alongside its title using plt.subplot(), plt.title(), plt.imshow(), plt.axis(), and plt.show().

### Step 8:

End the program.

## Program:

```python

Developed By: Javith Farkhan S
Register Number:212221240017
Program to segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

```

```python 

# Load the necessary packages:

import cv2
import matplotlib.pyplot as plt
import numpy as np

```

```python

# Read the Image and convert to grayscale:

image=cv2.imread("carss.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

```

```python

# Use Global thresholding to segment the image:

ret, thresh1 = cv2.threshold(image1,100,220,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,90,160, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,140,220,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,225,270,cv2.THRESH_TOZERO_INV)

```

```python

# Use Adaptive thresholding to segment the image:

th1 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 3)
th2 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 3)

```

```python

# Use Otsu's method to segment the image:

ret2, th3 = cv2.threshold(image1, 150, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)

```

```python

# Display the results:

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (Truncate)",
       "Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)","Otsu"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
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


## Output:

### Original Image:

![Di9 1](https://github.com/Javith-farkhan/Thresholding/assets/94296805/47ecaeb1-11d4-40bb-b863-23260b705036)


### Global Thresholding:

![di9 2](https://github.com/Javith-farkhan/Thresholding/assets/94296805/77d63281-93a8-4c88-bd5a-b2063b67e5f3)

![Di9 3](https://github.com/Javith-farkhan/Thresholding/assets/94296805/6579a32e-c5ce-40ac-9b79-d4c0008c7f5d)

![Di9 4](https://github.com/Javith-farkhan/Thresholding/assets/94296805/5be34dfa-9930-4643-983f-7d41c5160cb4)

![Di9 5](https://github.com/Javith-farkhan/Thresholding/assets/94296805/ee81cfcd-5866-4065-82d1-7485f6e7ac71)

![Di9 6](https://github.com/Javith-farkhan/Thresholding/assets/94296805/a257c2c2-fa7c-4caf-ab4d-e59b17cee122)


### Adaptive Thresholding:

![Di9 7](https://github.com/Javith-farkhan/Thresholding/assets/94296805/6c0aa75d-4957-413d-815c-115a3cdbdd6e)

![Di9 8](https://github.com/Javith-farkhan/Thresholding/assets/94296805/113d1393-1f91-4de6-b898-6f2eb1f36621)



### Optimum Global Thesholding using Otsu's Method:

![Di9 9](https://github.com/Javith-farkhan/Thresholding/assets/94296805/a2101fba-9db6-4d3a-91b1-6fae9e92ab28)



## Result

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

