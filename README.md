```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn6_.tif') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3) 
sobel_edge = cv2.magnitude(sobel_x, sobel_y) 
laplacian_edge = cv2.Laplacian(gray_image, cv2.CV_64F)
canny_edge = cv2.Canny(gray_image, 100, 200) 
plt.subplot(2, 2, 2)
plt.imshow(laplacian_edge, cmap='gray')
plt.title("Laplacian Edge Detector")
plt.axis('off')
plt.subplot(2, 2, 3)
plt.imshow(canny_edge, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.tight_layout()
plt.show()
```
