# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

## Program:
```
Developed By: Kishore N
Register Number: 212222240049
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('varta mamey.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
```
```
# Plot the original and transformed images
plt.figure(figsize=(12, 8))

plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193727](https://github.com/user-attachments/assets/a15087f5-adb7-4de0-b01a-dcd2e787f378)

i)Image Translation
```
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193733](https://github.com/user-attachments/assets/b34f21d1-c095-4146-b61e-790b24029e93)

ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193739](https://github.com/user-attachments/assets/ef877c37-5456-408a-b8cc-5f867a300632)

iii)Image shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193744](https://github.com/user-attachments/assets/6ee9dda4-063c-433d-b04d-900acb1a6b74)

iv)Image Reflection
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193753](https://github.com/user-attachments/assets/0596ea44-9ced-4e48-9bc4-2d9012261023)

v)Image Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193801](https://github.com/user-attachments/assets/536d7ec0-2862-4400-b233-71b23596028b)

vi)Image Cropping
```
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 193807](https://github.com/user-attachments/assets/9f52bc29-3d90-469c-ac35-125dea05e550)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
