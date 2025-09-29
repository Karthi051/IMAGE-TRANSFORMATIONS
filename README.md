# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.


## Program:
### Developed By:KARTHIKEYAN K
### Register Number:212223230101
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Karthi photo.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))


scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 


M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))


reflected_image = cv2.flip(image_rgb, 1) 



M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1) 
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))


cropped_image = image_rgb[50:300, 100:400] 

plt.figure(figsize=(12, 8))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

plt.subplot(2, 3, 2)
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')

plt.subplot(2, 3, 3)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')

plt.subplot(2, 3, 4)
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')

plt.subplot(2, 3, 5)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

plt.subplot(2, 3, 6)
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()

```
## Output:
<img width="1170" height="793" alt="46105ec5-134e-493e-8230-65dbd6417268" src="https://github.com/user-attachments/assets/991a9968-63a7-4271-ba39-0a3cae6f51ac" />
<img width="330" height="300" alt="13f1d0ac-e4f1-4eb5-9202-2797f78986a2" src="https://github.com/user-attachments/assets/bd27ac8f-811b-4dab-8e24-0ca615860fac" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
