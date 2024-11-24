# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText
### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation



 
## Program:
```
Name : Vaishnav Nanda
Register no :212222240112
```

#### Import the necessary packages

``` Python
import numpy as np
import cv2
import matplotlib.pyplot as plt
```

#### Read and show the Original image

``` Python
image = cv2.imread("fingerprint.png")
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```



#### Use Opening operation

```
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")
```


#### Use Closing Operation

```
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")


```
## Output:

### Display the Original Image

![Screenshot 2024-11-24 150358](https://github.com/user-attachments/assets/ec26878f-dc68-4f16-a314-03aa8e2fb797)



### Display the result of Opening

![Screenshot 2024-11-24 150405](https://github.com/user-attachments/assets/6ef68aee-f32f-492c-91f7-720a37bb2808)

### Display the result of Closing

![Screenshot 2024-11-24 150418](https://github.com/user-attachments/assets/18c9126b-a660-4be7-be5b-1661e5fe44fa)



## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
