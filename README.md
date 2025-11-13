# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>Read the image and convert it to grayscale.

### Step2:
<br>Apply global thresholding with a fixed value.

### Step3:
<br>Apply adaptive thresholding for local regions.

### Step4:
<br>Apply Otsu’s method for automatic threshold selection.

### Step5:
<br>Display all results using Matplotlib.

## Program

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('dog.png')
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

_, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)
adaptive = cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                 cv2.THRESH_BINARY, 11, 2)
_, otsu = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

titles = ['Original Image', 'Global Thresholding', 'Adaptive Thresholding', "Otsu's Method"]
images = [cv2.cvtColor(img, cv2.COLOR_BGR2RGB), global_thresh, adaptive, otsu]

plt.figure(figsize=(8, 6))
for i in range(4):
    plt.subplot(2, 2, i + 1)
    cmap = 'gray' if i > 0 else None
    plt.imshow(images[i], cmap=cmap)
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()

```
## Output

### Original Image
<img width="393" height="297" alt="image" src="https://github.com/user-attachments/assets/c5c11b6b-fc25-420e-b1d3-c250e36867f4" />


### Global Thresholding
<img width="411" height="290" alt="image" src="https://github.com/user-attachments/assets/3235b507-7a69-40da-9cc1-92cd9e9b268d" />


### Adaptive Thresholding
<img width="380" height="284" alt="image" src="https://github.com/user-attachments/assets/23fe4af2-054f-4686-be77-d4ecb214ce08" />


### Optimum Global Thesholding using Otsu's Method
<img width="398" height="301" alt="image" src="https://github.com/user-attachments/assets/a7c87f70-d82f-494a-a015-2f972338cebc" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
