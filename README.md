# Ex.-No-03-Histogram-of-an-Images
---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
### Name: Eesha Ranka
### Register No:212224240040

```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('img1.jpeg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Orginal img')
plt.show()
img = cv2.imread('img1.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Enhanced img');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

<img width="311" height="433" alt="download" src="https://github.com/user-attachments/assets/a8926133-eb92-4c6c-8ec5-c499a3de74ff" />

   
- Histogram of original grayscale image is plotted

<img width="578" height="433" alt="download" src="https://github.com/user-attachments/assets/c55e3fed-dcf3-4e6f-94d3-a1c7b27d9c1c" />

 
- Enhanced image after histogram equalization is displayed

<img width="311" height="433" alt="download" src="https://github.com/user-attachments/assets/9e1bbd8f-fc52-4bd6-9a0a-52c491dcbf19" />

  
- Histogram of enhanced grayscale image shows improved contrast

<img width="578" height="433" alt="download" src="https://github.com/user-attachments/assets/d0ad8cf6-6671-4f24-8f87-5cfd98d9766d" />


### Color Image Histogram Equalization

- Original color image and Enhanced image after HSV-based equalization is displayed  

<img width="1144" height="414" alt="download" src="https://github.com/user-attachments/assets/ed271f03-e70c-4211-9447-af7670a9db7a" />


- Histogram of B, G, R channels is plotted and  Histogram of enhanced image shows better intensity distribution  

<img width="1245" height="372" alt="download" src="https://github.com/user-attachments/assets/4eb3be6e-2869-4bbf-8dc0-d775ac2df074" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
