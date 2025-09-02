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
# Developed By: HEMAVATHY S
# Register Number: 212223230076
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load image
image = cv2.imread('/content/image.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Histogram before equalization
hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

# Equalized image
equalized_image = cv2.equalizeHist(gray_image)
hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

plt.figure(figsize=(10, 7))

# Original grayscale image
plt.subplot(2, 2, 1)
plt.imshow(gray_image, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')

# Equalized image
plt.subplot(2, 2, 2)
plt.imshow(equalized_image, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')

# Original histogram (bars instead of line)
plt.subplot(2, 2, 3)
plt.plot(hist_original / hist_original.max(), color='black')

plt.bar(range(256), hist_original.ravel(), width=1.0, color='black')
plt.title('Original Histogram')
plt.xlim([0, 256])

# Equalized histogram (bars instead of line)
plt.subplot(2, 2, 4)
plt.bar(range(256), hist_equalized.ravel(), width=1.0, color='black')
plt.title('Equalized Histogram')
plt.xlim([0, 256])

plt.tight_layout()
plt.show()
```
## Output:
### Input Grayscale Image and Color Image
<img width="594" height="410" alt="image" src="https://github.com/user-attachments/assets/3a907937-c32f-4985-bbe2-b7d830f131bf" />
<img width="509" height="342" alt="image" src="https://github.com/user-attachments/assets/547abb46-a878-4129-a9df-6a4398e90fa8" />


### Histogram of Grayscale Image and any channel of Color Image
<img width="489" height="684" alt="image" src="https://github.com/user-attachments/assets/2a3054b3-e868-4187-8450-9ecec972522e" />

### Histogram Equalization of Grayscale Image.
<img width="560" height="689" alt="image" src="https://github.com/user-attachments/assets/151e63b9-3972-4091-ba45-95bd2d3bb867" />

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
