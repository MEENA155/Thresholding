# Thresholding of Images
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
Use Otsu's method to segment the image.

### Step6:
Display the results.
## Program
'''
Developed by :MEENA.S
Register Number :212221240028.
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt




# Read the Image and convert to grayscale

image=cv2.imread("porsche.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("porsche.jpg",0)


# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)



# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)



# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)",
"Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu",
       "Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,
thresh_img6,thresh_img7,thresh_img8]
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
![image](https://user-images.githubusercontent.com/94677128/171351148-b6b2a7a6-c705-47a9-b300-f9a3e5b39712.png)


### Global Thresholding
![image](https://user-images.githubusercontent.com/94677128/171351231-b9fe347c-825f-47a4-b525-83d9ec04c2d9.png)
![image](https://user-images.githubusercontent.com/94677128/171351287-3ef187c6-f31f-4237-af0e-6b966c1f4ee5.png)
![image](https://user-images.githubusercontent.com/94677128/171351351-30244ed2-c474-47b1-8d03-390132255084.png)
![image](https://user-images.githubusercontent.com/94677128/171351448-6eb3dbe2-2456-42b6-b446-4877784a4f78.png)


### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/94677128/171351604-359979b6-6b9d-404e-b913-93d0f201433f.png)
![image](https://user-images.githubusercontent.com/94677128/171351646-88001f3e-9921-4ac5-a58f-d66bdcbcb2a4.png)


### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/94677128/171351738-00733755-ad1c-4d59-b7e7-1f1e1be0f575.png)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

