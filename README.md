# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

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
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
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
# Step 4: Apply Sobel operator
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
sobel = cv2.magnitude(sobel_x, sobel_y)
sobel = cv2.convertScaleAbs(sobel)
```
```python
# Step 5: Apply Prewitt operator using custom kernels
prewitt_x = np.array([[-1, 0, 1],
                      [-1, 0, 1],
                      [-1, 0, 1]], dtype=np.float32)

prewitt_y = np.array([[-1, -1, -1],
                      [ 0,  0,  0],
                      [ 1,  1,  1]], dtype=np.float32)

px = cv2.filter2D(gray, cv2.CV_32F, prewitt_x)
py = cv2.filter2D(gray, cv2.CV_32F, prewitt_y)
prewitt = cv2.magnitude(px, py)
prewitt = cv2.convertScaleAbs(prewitt)
```
```python
# Step 6: Apply Roberts operator using custom kernels
roberts_x = np.array([[1, 0],
                      [0, -1]], dtype=np.float32)

roberts_y = np.array([[0, 1],
                      [-1, 0]], dtype=np.float32)

rx = cv2.filter2D(gray, cv2.CV_32F, roberts_x)
ry = cv2.filter2D(gray, cv2.CV_32F, roberts_y)
roberts = cv2.magnitude(rx, ry)
roberts = cv2.convertScaleAbs(roberts)
```
```python
# Step 7: Apply Laplacian operator
laplacian = cv2.Laplacian(gray, cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian)
```
```python
# Step 8: Apply Canny edge detector
canny = cv2.Canny(gray, 100, 200)
```
```python
# Step 9: Display all edge-detected images for comparison
plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title('Original Image')
plt.axis('off')

plt.subplot(2, 3, 2)
plt.imshow(sobel, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

plt.subplot(2, 3, 3)
plt.imshow(prewitt, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')

plt.subplot(2, 3, 4)
plt.imshow(roberts, cmap='gray')
plt.title('Roberts Edge Detection')
plt.axis('off')

plt.subplot(2, 3, 5)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

plt.subplot(2, 3, 6)
plt.imshow(canny, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map  

###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel  
- Detects directional edges  

###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise  

###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  
<img width="278" height="478" alt="image" src="https://github.com/user-attachments/assets/8e8836cc-f334-41f4-b44f-366987a10be6" />

<img width="1332" height="553" alt="image" src="https://github.com/user-attachments/assets/b9bc27bb-f569-40d9-bc01-d051efd8fc82" />

<img width="1376" height="573" alt="image" src="https://github.com/user-attachments/assets/b8131d55-277c-45f1-b98e-08303f12c3bc" />



---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
