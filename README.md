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
Load the necessary packages.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image.
### Step6:
Display the results.
## Program
```
Developed by: BASKARAN V
Register No: 212222230020
```
```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("OPEN.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("OPEN.png",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results
```
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
![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/c9691e01-f33b-4084-a18b-a88b39e5f916)


### Global Thresholding
![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/98735b16-ac28-4228-bfd5-ed29097e4643)

![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/89fcfbc5-5a12-4e47-ba27-0a42fc8624c0)

![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/88c6417a-a05e-4ec0-bdd1-b45b44f0acd7)

![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/0d911d71-294e-4398-9912-25d0e43e5140)

![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/07107b9b-2db1-475e-9a70-91d489fc3f5f)

### Adaptive Thresholding
![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/3851f267-f43d-4799-b0e0-553b22a7a485)

![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/6e0b1c02-c02a-4ef5-877f-d17d34a767df)


### Optimum Global Thesholding using Otsu's Method
![download](https://github.com/BaskaranV15/THRESHOLDING/assets/118703522/08cecbb0-744e-40e2-9900-df6fd88d94b9)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

