# canny-edge-detection-

## Aim

To perform edge detection using Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Canny edge detector** using OpenCV.

### Step 5:
Display all edge-detected images for comparison.

---

## Developed By

- **Name:** JANAGIRAMAN M  
- **Register No:** 212224230101

---

## PROGRAM :
```python
# Step 1: Import all the necessary modules
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
# Step 2: Load an image using cv2.imread()
image = cv2.imread('jack and rose.jpg')

if image is None:
    raise FileNotFoundError("red.jpg was not found. Place red.jpg in the same folder as this notebook.")

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
```python
# Step 3: Convert the image to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(6, 5))
plt.imshow(gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

```python
# Step 4: Apply Canny edge detector
canny = cv2.Canny(gray, 100, 200)
```
```python
# Step 5: Display all edge-detected images for comparison
plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title('Original Image')
plt.axis('off')


plt.subplot(2, 3, 6)
plt.imshow(canny, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output


###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  
<img width="278" height="478" alt="image" src="https://github.com/user-attachments/assets/8e8836cc-f334-41f4-b44f-366987a10be6" />


<img width="285" height="442" alt="image" src="https://github.com/user-attachments/assets/d57d0c50-9b38-489c-bd24-417517a3b7a3" /><img width="263" height="438" alt="image" src="https://github.com/user-attachments/assets/1e78fe9c-7f16-4b14-8d20-1bb722cb455f" />



---

## Result

Thus, edges are successfully detected using Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
