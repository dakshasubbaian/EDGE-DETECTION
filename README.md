# EX. No: 6 – Edge Detection Using OpenCV
## Developed by:
## Name: DAKSHA SUBBAIAN
## Register number:212223230036

## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

The program performs the following operations:

- Read and display an input image.
- Convert the image into grayscale.
- Apply Sobel edge detection.
- Apply Laplacian edge detection.
- Apply Canny edge detection.
- Display all edge-detected images for comparison.

## Software Required

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Import all the necessary modules for the program.

**Step 2:** Load an image using `cv2.imread()`.

**Step 3:** Convert the image to grayscale using `cv2.cvtColor()`.

**Step 4:** Apply the Sobel operator using OpenCV to detect edges in the horizontal and vertical directions.

**Step 5:** Combine the Sobel X and Y gradients using `cv2.magnitude()`.

**Step 6:** Apply the Laplacian operator using OpenCV.

**Step 7:** Apply the Canny edge detector using `cv2.Canny()`.

**Step 8:** Display all edge-detected images for comparison.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the input image
image = cv2.imread('images.jpeg')

# Convert image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()


# 1. Sobel Edge Detection

sobel_x = cv2.Sobel(
    gray_image, cv2.CV_64F, 1, 0, ksize=5
)

sobel_y = cv2.Sobel(
    gray_image, cv2.CV_64F, 0, 1, ksize=5
)

# Combine both directions
sobel_combined = cv2.magnitude(sobel_x, sobel_y)

plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
plt.show()


# 2. Laplacian Edge Detection

laplacian = cv2.Laplacian(
    gray_image, cv2.CV_64F
)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()


# 3. Canny Edge Detection

canny_edges = cv2.Canny(
    gray_image, 50, 150
)

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```

## Output

<img width="221" height="342" alt="image" src="https://github.com/user-attachments/assets/8193f1aa-5a93-48c2-aaac-7095358658c0" />

<img width="216" height="341" alt="image" src="https://github.com/user-attachments/assets/54395698-d868-4a80-9a83-8f04f6aee524" />

<img width="217" height="342" alt="image" src="https://github.com/user-attachments/assets/ebc556b4-96b6-4204-b845-cc369ac3635a" />

<img width="221" height="337" alt="image" src="https://github.com/user-attachments/assets/04e9cbe8-7a3c-4aaa-8491-69ced62898fc" />


## Result

Thus, edges are successfully detected using Sobel, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and image analysis.
