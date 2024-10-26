# EX-10:OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:Read the Image:

Load the input color image from a specified path.
### Step-2:Convert to Grayscale:

Transform the color image into a grayscale format for easier processing.
### Step-3:Edge Detection:

Apply an edge detection technique to identify the prominent edges in the grayscale image.
### Step-4:Create Structuring Element:

Define a kernel (structuring element) for use in morphological operations, typically a matrix of ones.
### Step-6:Morphological Operations:

Perform morphological operations:<br>
Opening: Remove small objects from the edges to clean up the image.<br>
Closing: Fill small holes in the detected edges to enhance the structure.
### Step-7:Display Results:

Show the original grayscale image, along with the results of the opening and closing operations for visual comparison.

 
## Program:
```
Developed By : VAISHNAV NANDA
Reference Number: 212222240112
```
# Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
# Create the Text using cv2.putText
```
input_image_path = 'cart.jpg'
color_image = cv2.imread(input_image_path)
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image,cmap="gray")
edges = cv2.Canny(gray_image, 100, 200)
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)
erosion = cv2.erode(edges, kernel, iterations=1)
dilation = cv2.dilate(edges, kernel, iterations=1)
```

# Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2,2,1)
plt.imshow(gray_image)
plt.title('Original Color Image')
plt.axis('off')
```
![alt text](image-1.png)
# Use Opening operation
```
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('off')
```
![alt text](image-2.png)

# Use Closing Operation
```
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('off')
plt.show()
```
![alt text](image-3.png)

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
