# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Code 

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Qn_7_.jpg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output
### Input image and grayscale image
![image](https://github.com/user-attachments/assets/08f8f281-ed33-43fd-8b7b-4e0e7a0cc6f7)
![image-1](https://github.com/user-attachments/assets/b2e73e3f-c3c5-448c-8e24-cb5bd576052e)

### Canny Edge detector output
![image-2](https://github.com/user-attachments/assets/68e118a4-ba3e-4ca0-88b7-9e695a297e6c)

### Display the result of Hough transform
![image-3](https://github.com/user-attachments/assets/b0747f5a-1fc4-481a-9681-175c086f2b34)

## Result

Thus,The Python program to detect the lines using Hough Transform run successfully.
