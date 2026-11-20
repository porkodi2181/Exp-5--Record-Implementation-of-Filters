## EXP. 5 – IMPLEMENTATION OF FILTERS USING OPENCV

## NAME  : PORKODI B
## REG NO : 212224240114

## Aim

To implement different smoothing and sharpening filters using OpenCV and Python to enhance image quality and display the filtered images for comparison.

## Software Requirements

- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Filters Implemented

### Smoothing Filters
1. Average Filter
2. Weighted Average Filter
3. Gaussian Filter
4. Median Filter

### Sharpening Filters
1. Laplacian Kernel
2. Laplacian Operator

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the image from BGR to RGB format.
4. Apply the Average Filter using a custom kernel.
5. Apply the Weighted Average Filter using a weighted kernel.
6. Apply the Gaussian Filter using `cv2.GaussianBlur()`.
7. Apply the Median Filter using `cv2.medianBlur()`.
8. Apply the Laplacian Kernel using `cv2.filter2D()`.
9. Apply the Laplacian Operator using `cv2.Laplacian()`.
10. Display the original and processed images separately.

## Implementation

### 1. Import Libraries

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
```

### 2. Read the Input Image

```python
image1 = cv2.imread("Image.png")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
```

## OUTPUT:



### 3. Average Filter

```python
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
```

## OUTPUT:


### 4. Weighted Average Filter

```python
kernel1 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16

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
```

## OUTPUT:


### 5. Gaussian Filter

```python
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
```

## OUTPUT:

### 6. Median Filter

```python
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
```

## OUTPUT:

### 7. Laplacian Kernel

```python
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
```

## OUTPUT:


### 8. Laplacian Operator

```python
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
```

## Output




## Result

Thus, different smoothing and sharpening filters were successfully implemented using OpenCV and Python. Smoothing filters reduce noise, while sharpening filters enhance image edges and details.
