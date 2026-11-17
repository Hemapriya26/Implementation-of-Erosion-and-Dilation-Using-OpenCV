# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create a blank image using NumPy.

### Step 3:

Insert text onto the image using OpenCV's text drawing function.

### Step 4:

Display the original image.

### Step 5:

Create a structuring element (kernel) of suitable size.

### Step 6: Image Erosion

- Apply the erosion operation using the created kernel.
- Remove pixels from the boundaries of foreground objects.
- Display the eroded image.

### Step 7: Image Dilation

- Apply the dilation operation using the same kernel.
- Add pixels to the boundaries of foreground objects.
- Display the dilated image.

### Step 8:

Compare the original, eroded, and dilated images.

## Program
```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a black blank image
img = np.zeros((300, 500), dtype=np.uint8)

# Insert white text
cv2.putText(
    img,
    "IMAGE   PROCESSING",
    (40, 150),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    255,
    3
)

# Display original image
plt.imshow(img, cmap="gray")
plt.title("Original Image")
plt.axis("off")
plt.show()

# Create a 5x5 kernel
kernel = np.ones((5, 5), dtype=np.uint8)

print(kernel)

# Select only the word IMAGE
roi = img[110:165, 35:180]

# Apply erosion only to IMAGE
eroded = cv2.erode(roi, kernel, iterations=1)
erosion = img.copy()
erosion[110:165, 35:180] = eroded

# Display eroded image
plt.imshow(erosion, cmap="gray")
plt.title("Eroded Image")
plt.axis("off")
plt.show()

# Apply dilation only to IMAGE
dilated = cv2.dilate(roi, kernel, iterations=1)
dilation = img.copy()
dilation[110:165, 35:180] = dilated

# Display dilated image
plt.imshow(dilation, cmap="gray")
plt.title("Dilated Image")
plt.axis("off")
plt.show()

# Compare all three images
plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap="gray")
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(erosion, cmap="gray")
plt.title("Eroded Image")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(dilation, cmap="gray")
plt.title("Dilated Image")
plt.axis("off")

plt.tight_layout()
plt.show()

```

## Developed By

**Name: Hemapriya P** 

**Register No: 212225040126**

## Output

### Original Image

- A text image containing characters is displayed.
- The image serves as the input for morphological processing.
  
  <img width="677" height="546" alt="image" src="https://github.com/user-attachments/assets/246a9202-b420-4905-922a-be22d8d77707" />


### Erosion

- Original image is displayed.
- Eroded image is displayed.
- The thickness of the characters is reduced.
- Object boundaries shrink inward.

  <img width="700" height="432" alt="image" src="https://github.com/user-attachments/assets/9970c6ed-33db-46cf-9a8e-1c17c8c9ef36" />


### Dilation

- Original image is displayed.
- Dilated image is displayed.
- The thickness of the characters increases.
- Object boundaries expand outward.

 <img width="715" height="435" alt="image" src="https://github.com/user-attachments/assets/7050a213-16f3-4ec4-869d-7583b846da79" />

## Result

Thus, the morphological operations **Erosion** and **Dilation** are successfully implemented using OpenCV.
