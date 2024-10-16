# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

### Step1:
Initialize an Empty Image:
Create a black image of size 100x600 pixels.

### Step2:
Add Text to the Image:
Use a specified font to write the word "Dhiyaneshwar" on the image at a defined position.

### Step3:
Display the Original Image:
Show the image containing the text without axis labels.

### Step4:
Create Structuring Elements:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

### Step5:
Erode the Image:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.

### Step6:
Dilate the Image:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:
``` Python
DEVELOPED BY: MOUNESH P
REGISTER NO: 212222230084
```
### Import packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Create a blank image
```python
image = np.zeros((300, 600, 3), dtype="uint8")
```
### Create the text using cv2.putText
```python
text = "Mounesh"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
### Create a structuring element (5x5 rectangular)
```python
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
```
### Erode and Dilate the image
```python
eroded_image = cv2.erode(image, kernel, iterations=1)
dilated_image = cv2.dilate(image, kernel, iterations=1)
```
### Convert images from BGR to RGB for Matplotlib
```python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)
```
### Plot the original, eroded, and dilated images using Matplotlib
```python
plt.figure(figsize=(10, 5))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")

plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")

plt.tight_layout()
plt.show()
```
## Output:

### Display the input Image
![image](https://github.com/user-attachments/assets/58a64e5d-38d0-4c35-97f5-d15b558bb192)

### Display the Eroded Image
![image](https://github.com/user-attachments/assets/1b34da22-8c3c-4588-bebe-bb5fb97add82)

### Display the Dilated Image
![image](https://github.com/user-attachments/assets/832c884d-f77c-4c35-805a-37c22fe60ffe)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
