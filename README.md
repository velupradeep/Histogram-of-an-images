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
# Developed By: PRADEEP V
# Register Number: 212223240119
```


```


import cv2
import numpy as np
import matplotlib.pyplot as plt
gray_image = cv2.imread('th.jpeg', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
# Step 3: Plot the histogram of the grayscale image
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
# Step 4: Apply histogram equalization using OpenCV
equalized_gray_image = cv2.equalizeHist(gray_image)
# Step 5: Display the histogram of the equalized image
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
# Step 6: Display the enhanced grayscale image
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Get the input color image
color_image = cv2.imread('aj.jpg')
# Step 2: Display the input color image
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
# Step 3: Plot the histogram of the input color image (combined channels)
# Calculate the histogram for all channels separately
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
# Plot the histograms
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
plt.title("Histogram Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')
# Step 4: Apply histogram equalization to each channel of the color image
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
# Step 5: Merge the equalized channels back into a color image
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq]).








```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/09f6d62a-e9f8-49e5-a817-9096fe1ebfcd)
![image](https://github.com/user-attachments/assets/8b5fe959-cbb7-48f3-9ed9-9be8fcd90efd)




### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/8381199a-bc65-4c94-b396-1314ae6dfaa2)


![image](https://github.com/user-attachments/assets/f9b25c2a-3cba-4222-9ba2-a2d99b2b4e35)


### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/d287344a-0c42-47fb-a54a-ae3276615c95)

![image](https://github.com/user-attachments/assets/b17eb72b-bdc7-486a-853f-cb3c232a532c)






## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
