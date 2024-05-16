# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step1:
Import necessary packages
### Step2:
Create an empty window and add text to it

### Step3:
create a structuring element

### Step4:
Do the operation

### Step5:
Show the output image
 
## Program:

``` 
import cv2
import numpy as np
from matplotlib import pyplot as plt

input_image_path = 'sirisha.jpg'
color_image = cv2.imread(input_image_path)
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 100, 200)

kernel_size = 5  # Define the kernel size
kernel = np.ones((kernel_size, kernel_size), np.uint8)  # Corrected dtype

erosion = cv2.erode(edges, kernel, iterations=1)
dilation = cv2.dilate(edges, kernel, iterations=1)

plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap='gray')  # Corrected variable name
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')  # Corrected variable name
plt.title('Dilation')
plt.axis('on')

plt.show()



```
## Outputs:

![Screenshot 2024-05-16 181417](https://github.com/MavillaPranathi/erosion--dilation/assets/118343610/56afe307-8693-4799-a364-b3fceccf417c)

![Screenshot 2024-05-16 181458](https://github.com/MavillaPranathi/erosion--dilation/assets/118343610/0e095865-097e-4f6c-aefd-57b6dcb0cd8c)

![Screenshot 2024-05-16 181525](https://github.com/MavillaPranathi/erosion--dilation/assets/118343610/70c48c57-f904-4021-99fd-3a7fed760b68)

![Screenshot 2024-05-16 181610](https://github.com/MavillaPranathi/erosion--dilation/assets/118343610/43d7a1da-6f96-4bf0-b0eb-45f057524f63)

![Screenshot 2024-05-16 181651](https://github.com/MavillaPranathi/erosion--dilation/assets/118343610/abb942de-8922-4547-8460-9d0b0f013e81)



## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
