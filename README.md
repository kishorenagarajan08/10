# Opening and Closing Operations Using OpenCV


## Developed By

**Name:** KISHORE N

**Register No:** 212223230106
## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

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

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.


## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')

# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Closing Operation")
plt.axis('off')
```

## Output
<img width="522" height="505" alt="image" src="https://github.com/user-attachments/assets/1b4c6a7a-426d-4af8-809d-d7782d571ddc" />
<img width="616" height="521" alt="image" src="https://github.com/user-attachments/assets/d72a1a6b-0eef-4746-bb8c-0a29eadaa030" />
<img width="585" height="507" alt="image" src="https://github.com/user-attachments/assets/dcdc8665-db6a-4cd4-9322-35e55c579c78" />

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
