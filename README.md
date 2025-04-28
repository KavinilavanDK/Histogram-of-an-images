# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: KAVI NILAVAN DK
# Register Number: 212223230103

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image safely
grayscale_image = cv2.imread("th.jpg", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("th.jpg")

# Check if images are loaded
if grayscale_image is None or color_img is None:
    print("Error: Image could not be loaded.")
    exit()

# Calculate histograms
gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])

# Plot images
plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')
plt.show()

# Plot histograms
plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")

plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red')
plt.plot(hist_g, color='green')
plt.plot(hist_b, color='blue')
plt.title("Color Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")
plt.show()
 






```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/77d83fb4-139f-44ba-ac55-d60407b5c3a0)


### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/94972f6e-997c-460b-b9fe-4c9e6f79bea0)



### Histogram Equalization of Grayscale Image.
![image](https://github.com/user-attachments/assets/7df2127a-340e-4802-9ada-62bcb128321f)




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
