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

## Developed By: DIVYA K
## Register Number: 212222230035
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

i)Image Translation

image = cv2.imread('fish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

ii) Image Scaling

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 


iii)Image shearing

M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))


iv)Image Reflection

reflected_image = cv2.flip(image_rgb, 1) 


v)Image Rotation

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1) 
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

vi)Image Cropping

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
### i)Image Translation

![image](https://github.com/user-attachments/assets/e567c250-fa5c-463a-aff3-73494d8b6b0c)

![image](https://github.com/user-attachments/assets/cad25ca0-b8a9-46e3-9263-2c6b842a9fee)

### ii) Image Scaling

![image](https://github.com/user-attachments/assets/97e1c248-c2a0-4edd-a0c3-c624dd3bdf21)

### iii)Image shearing

![image](https://github.com/user-attachments/assets/8235ed2d-c165-440d-974c-062d686db60e)


### iv)Image Reflection

![image](https://github.com/user-attachments/assets/0755985c-b4d1-48cc-acc1-444ddbed711b)


### v)Image Rotation

![image](https://github.com/user-attachments/assets/866791a6-b6f6-4d73-9c21-91d65881fd18)

### vi)Image Cropping

![image](https://github.com/user-attachments/assets/7f34cdde-5d7e-4a8b-889c-3b5f6cca6a8d)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
