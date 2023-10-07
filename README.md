# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import the necessary packages.
<br>

### Step2:
Create the text using cv2.putText.
<br>

### Step3:
Create the structuring element.
<br>

### Step4:
Erode the image using cv2.erode().
<br>

### Step5:
Dilate the imge using cv2.dilate().
<br>

## Program:
```
DEVELOPED BY :IYYANAR S
REG NO: 212222240036
```


# Load the necessary packages:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale:
```
image=cv2.imread("gt.jpeg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
grayscale_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(grayscale_image,'gray')
plt.title('Gray image')
plt.axis('off')
```








# Use Global thresholding to segment the image:
```
ret,thresh_img1=cv2.threshold(grayscale_image,81,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(grayscale_image,81,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(grayscale_image,81,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(grayscale_image,80,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(grayscale_image,105,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image:
```
thresh_img7=cv2.adaptiveThreshold(grayscale_image,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(grayscale_image,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Use Otsu's method to segment the image :
```
ret,thresh_img6=cv2.threshold(grayscale_image,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results:
```
titles=["Gray Image", "Threshold Image (Binary)", "Threshold Image (Binary Inverse)", "Threshold Image (To Zero)"
       , "Threshold Image (To Zero-Inverse)", "Threshold Image (Truncate)", "Otsu", "Adaptive Threshold (Mean)", "Adaptive Threshold (Gaussian)"]
images=[grayscale_image, thresh_img1, thresh_img2, thresh_img3, thresh_img4, thresh_img5, thresh_img6, thresh_img7, thresh_img8]

for i in range(0,9):
    plt.figure(figsize=(5,5))
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
![1d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/c7f606e9-db40-4ad7-b4ac-6834d00c823b)

<br>
<br>
<br>
<br>
<br>

### Global Thresholding:
![2d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/49e9df3f-7d65-4a32-a819-a078c0f7df6e)
![3d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/eb70cb06-698e-4280-a478-a2e81229dc9a)
![4d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/22a80b90-debd-4c8c-ab96-9f391586ca76)
![5d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/015badfe-b8f2-43ec-80d4-d62a8e024c0f)
![6d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/c7cc864a-36eb-430d-a338-a7249f810fe2)
<br>
<br>
<br>
<br>
<br>

### Adaptive Thresholding:
![7d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/69f7638e-94e3-4f63-8f64-75cc96d09275)
![8d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/23be00a6-6faf-4a0c-8b56-5eb2854467c4)


<br>
<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method:
![9d](https://github.com/Iyyanar22009120/THRESHOLDING/assets/118680259/d533d62e-efbb-4f23-8dec-e84ba1a5d6d2)
<br>
<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
