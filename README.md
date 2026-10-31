# Exp-4--Record-Image-Transformations
---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
### Name: JANANI S
### Register No: 212224230103

## Load the image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:/Users/admin/OneDrive/Documents/Downloads/image 4.png")
```
## Display the original image
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")  
plt.axis('off')
```
## image translation
```
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')
```
## Image scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```
## Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image") 
plt.axis('off')
```
## Image Reflection
```
reflected_image = cv2.flip(image, 2) 
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) 
plt.title("Reflected Image")  
plt.axis('off')
```
## Image rotation
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
## Image cropping
```
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")  
plt.axis('off')

```
##  Output

<img width="840" height="682" alt="Screenshot 2026-10-28 154703" src="https://github.com/user-attachments/assets/59f4ad01-6bfd-4ef5-a68c-0b6f1d6ca6c4" />
<img width="393" height="630" alt="Screenshot 2026-10-28 154719" src="https://github.com/user-attachments/assets/78a4f819-0571-46b7-8565-7409e95b16ab" />
<img width="775" height="600" alt="Screenshot 2026-10-28 154726" src="https://github.com/user-attachments/assets/e7eebd79-e567-46d3-b7a0-f674676b751a" />
<img width="342" height="621" alt="Screenshot 2026-10-28 154735" src="https://github.com/user-attachments/assets/230cd5c8-44e7-4af0-9a96-330358e55729" />
<img width="340" height="617" alt="Screenshot 2026-10-28 154744" src="https://github.com/user-attachments/assets/86a7b7f9-6697-4a22-8274-5a34eeeec2e3" />
<img width="327" height="616" alt="Screenshot 2026-10-28 154752" src="https://github.com/user-attachments/assets/a388466b-6081-45da-be9c-000fa972b27e" />
<img width="390" height="630" alt="Screenshot 2026-10-28 154801" src="https://github.com/user-attachments/assets/f68519bc-d544-43d9-9781-1e07b522e021" />




### Image Translation
- Original image is displayed  
- Translated image (shifted right and down) is displayed  

### Image Scaling
- Original image is displayed  
- Downscaled image (0.5×) is displayed  
- Upscaled image (2×) is displayed  

### Image Shearing
- Original image is displayed  
- Horizontally sheared image is displayed  
- Vertically sheared image is displayed  

### Image Reflection
- Original image is displayed  
- Horizontally flipped image is displayed  
- Vertically flipped image is displayed  
- Both-axis flipped image is displayed  

### Image Rotation
- Original image is displayed  
- 45° rotated image is displayed  
- 90° rotated image is displayed  

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
