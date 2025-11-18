# 🔵 **Logical Operations on a Color Image Using Binary Masks**

## 📘 Overview

This project demonstrates the application of **logical (bitwise) operations** on a **color image** using a **binary mask**. Logical operations are fundamental in digital image processing, enabling selective region processing, segmentation, noise removal, and region-of-interest (ROI) manipulation.

The code performs and visualizes the following bitwise operations:

- **AND**
- **OR**
- **XOR**
- **NOT**

Each operation is applied between a **color image** and a **mask** that covers the **top-left region** of the image. The output images highlight how each logical operation modifies pixel values.

## 🎯 Objectives

- Understand bitwise operations on multi-channel color images.
- Apply a binary mask for region selection.
- Visualize logical results such as masking, highlighting, and inversion.
- Strengthen conceptual knowledge for image processing coursework.

## 🛠️ Technologies Used

- Python  
- OpenCV  
- NumPy  
- Matplotlib  

## 📂 Project Structure

```
Assignment/
│
├── image.jpg                # Input image
├── Assignment1.ipynb        # Notebook
├── README.md                # Documentation
```

## 🧪 Logical Operations Implemented

### 1️⃣ Bitwise AND
Keeps pixels where both the image and mask are non-zero.

### 2️⃣ Bitwise OR
Highlights the mask region by combining intensities.

### 3️⃣ Bitwise XOR
Shows differences between the mask and the image.

### 4️⃣ Bitwise NOT
Inverts the entire image.

## 📎 Full Code

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread("image.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

rows, cols, _ = img.shape
mask = np.zeros((rows, cols), dtype=np.uint8)
mask[0:rows//2, 0:cols//2] = 255

mask_3 = cv2.merge([mask, mask, mask])

and_result = cv2.bitwise_and(img, mask_3)
or_result  = cv2.bitwise_or(img, mask_3)
xor_result = cv2.bitwise_xor(img, mask_3)
not_result = cv2.bitwise_not(img)

plt.figure(figsize=(12,10))

plt.subplot(3,2,1); plt.imshow(img); plt.title("Original Image"); plt.axis("off")
plt.subplot(3,2,2); plt.imshow(mask, cmap="gray"); plt.title("Mask"); plt.axis("off")
plt.subplot(3,2,3); plt.imshow(and_result); plt.title("Logical AND"); plt.axis("off")
plt.subplot(3,2,4); plt.imshow(or_result); plt.title("Logical OR"); plt.axis("off")
plt.subplot(3,2,5); plt.imshow(xor_result); plt.title("Logical XOR"); plt.axis("off")
plt.subplot(3,2,6); plt.imshow(not_result); plt.title("Logical NOT"); plt.axis("off")

plt.show()
```

## 📚 Learning Outcome

- Understanding of pixel-wise logical operations  
- Knowledge of region-based image masking  
- Practical experience with OpenCV  
- Strong conceptual clarity for viva and exams  

## 🧑‍💻 Author
**Priyam Bhattacharya**  
M.Sc. Computer Science, University of Calcutta  
