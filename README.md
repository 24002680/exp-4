# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
<br>
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
<br>
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically. 
5.Rotation rotates the image by a given angle.

### Step4:
<br>
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
<br>
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```
Developed By:gunasundari B
Register Number:212224040093

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Chennai_Central.jpg')


image.shape

plt.imshow(image[:,:,::-1])
plt.title('Original Image')
plt.show()
```
i)Image Translation
```

tx, ty = 100, 200
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
translated_image = cv2.warpAffine(image, M_translation, (636, 438)) 

plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis('on')
plt.show()
```
```
fx, fy = 2.0, 1.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(scaled_image[:,:,::-1]) 
plt.title("Scaled Image") 
plt.axis('on')
plt.show()
```
```

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (636, 438))

plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image") 
plt.axis('on')
plt.show()
```
```
reflected_image = cv2.flip(image, 2)


plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```
```

(height, width) = image.shape[:2] 
angle = 45
center = (width // 2, height // 2)
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 


plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image") 
plt.axis('off')

```
```
image .shape 

angle = 145  
center = (636 // 2, 438 // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) 
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 

plt.imshow(rotated_image[:,:,::-1])  
plt.title("Rotated Image")  
plt.axis('off')
plt.show()
```

```
x, y, w, h = 0, 0, 200, 150 
cropped_image = image[y:y+h, x:x+w] 


plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('on')

plt.subplot(1, 2, 2)
plt.imshow(cropped_image[:,:,::-1])
plt.title("Cropped Image")
plt.axis('on')

plt.tight_layout()
plt.show()
```


## Output:
### i)Image Translation
<br>
<br>
<br>
<br>

### ii) Image Scaling
<br>
<br>
<br>
<br>


### iii)Image shearing
<br>
<br>
<br>
<br>


### iv)Image Reflection
<br>
<br>
<br>
<br>



### v)Image Rotation
<br>
<br>
<br>
<br>



### vi)Image Cropping
<br>
<br>
<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
