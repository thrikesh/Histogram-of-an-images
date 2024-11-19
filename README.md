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
# Developed By: THRIKESWAR P
# Register Number: 212222230162

import cv2
from matplotlib import pyplot as plt

# Load the color image
image = cv2.imread('ajith.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(image_rgb)
plt.axis('off')
plt.title("Color Image")
plt.show()

hist_original = cv2.calcHist([image_rgb], [0], None, [256], [0, 256])

# Convert BGR to YUV
image_yuv = cv2.cvtColor(image, cv2.COLOR_BGR2YUV)

# Equalize the histogram of the Y channel
image_yuv[:, :, 0] = cv2.equalizeHist(image_yuv[:, :, 0])

# Convert YUV back to BGR
equalized_image = cv2.cvtColor(image_yuv, cv2.COLOR_YUV2BGR)

plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlim([0, 256])

hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')


```
## Output:
### Input Color Image
![image](https://github.com/user-attachments/assets/d07333d5-7ac4-4a34-b835-a3f82d0d1f38)



### Histogram of any channel of Color Image
![image](https://github.com/user-attachments/assets/f787eef9-165c-4b2a-b94c-244ef86364aa)




### Histogram Equalization of Color Image.
![image](https://github.com/user-attachments/assets/bb8e1ef1-750d-4f94-abd6-efc99d0e25e2)





## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
