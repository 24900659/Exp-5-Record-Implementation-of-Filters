# Exp-5-Record-Implementation-of-Filters

Image Smoothing and Sharpening Using OpenCV

Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

The program performs the following operations:

Read and display an input image
Apply Averaging filter
Apply Weighted Averaging filter
Apply Gaussian filter
Apply Median filter
Apply Laplacian sharpening using kernel
Apply Laplacian operator
Display all outputs for comparison

Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image (e.g., image.jpg).

Step 3:
Convert the image from BGR to RGB format for display.

Step 4:
Apply Averaging Filter using cv2.blur().

Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

Step 7:
Apply Median Filter using cv2.medianBlur().

Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

Step 10:
Display all filtered images using a grid layout for comparison.

Developed By

Name: MOHANA K.V.S.L

Reg.No: 212224240093

Program:
```
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("pic.jpeg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np.float32)/169
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()


kernel1 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
image3 = cv2.filter2D(image2, -1, kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()


gaussian_blur = cv2.GaussianBlur(image2, (33,33), 0, 0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()


median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()


kernel2 = np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3 = cv2.filter2D(image2, -1, kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()


laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
Output
image image image image image image
Smoothing Filters
Averaging filter produces blurred image
Weighted averaging provides smoother result with less distortion
Gaussian filter preserves edges better while reducing noise
Median filter removes salt-and-pepper noise effectively
Sharpening Filters
Laplacian kernel enhances edges and fine details
Laplacian operator detects edges clearly in grayscale
```
OUTPUT:

<img width="898" height="552" alt="image" src="https://github.com/user-attachments/assets/6e8e37d3-0932-425b-9bf9-e80d77b312b1" />

<img width="662" height="412" alt="image" src="https://github.com/user-attachments/assets/a9e883d4-a4b5-4366-a98f-d7cef0ea0dc7" />

<img width="645" height="407" alt="image" src="https://github.com/user-attachments/assets/6df1eef0-83ab-4204-bc70-d64585bae023" />

<img width="900" height="552" alt="image" src="https://github.com/user-attachments/assets/28d9e84b-be67-4ba1-9a75-75d14e2808ab" />

<img width="648" height="411" alt="image" src="https://github.com/user-attachments/assets/eef4ca63-f0d4-4c21-88d5-153269c387a8" />

<img width="645" height="405" alt="image" src="https://github.com/user-attachments/assets/fc6df85e-2253-4c17-9d13-541ee19390ff" />





Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
