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
![Screenshot 2024-10-05 192516](https://github.com/user-attachments/assets/be0477c4-04ae-4c49-b437-182403ac9109)

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
![Screenshot 2024-10-05 192529](https://github.com/user-attachments/assets/d2dcaf11-3886-442a-9cf9-e4a7a7607838)

ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 192536](https://github.com/user-attachments/assets/90998b55-addd-442a-aec6-cc574064778c)

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
![Screenshot 2024-10-05 192542](https://github.com/user-attachments/assets/e3cdfaf1-0103-43be-b3c2-4f13b29082ff)

iv)Image Reflection
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![Screenshot 2024-10-05 192548](https://github.com/user-attachments/assets/0f3e60f9-97da-4b11-8a74-afa2e3e4285b)

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
![Screenshot 2024-10-05 192554](https://github.com/user-attachments/assets/a39ebd2f-14c5-4640-9743-d0d896d570d8)

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
![Screenshot 2024-10-05 192600](https://github.com/user-attachments/assets/0130a102-6de9-42aa-8e94-40e4535b88cb)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
