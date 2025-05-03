# Exp-7-Edge-Linking-using-Hough-Transformm
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
## Program:
```
# Developed By: HARESH R
# Register Number: 212224040097
import cv2
import matplotlib.pyplot as plt
image = cv2.imread(r'C:\Users\admin\Downloads\eif.jpeg')  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```
![Screenshot 2025-05-03 110534](https://github.com/user-attachments/assets/75e5d38d-ff0e-4d72-becd-1453e00e2ede)

```
# Developed By: HARESH R
# Register Number: 212224040097

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

![Screenshot 2025-05-03 110545](https://github.com/user-attachments/assets/c2abbcde-08d6-4e93-892b-3242f830502b)


```
# Developed By: HARESH R
# Register Number: 212224040097

edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```
![Screenshot 2025-05-03 110557](https://github.com/user-attachments/assets/d45b41cc-96f3-4a2d-95cb-0cece78fa14e)


```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

```
```
# Developed By: HARESH R
# Register Number: 212224040097# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```
![Screenshot 2025-05-03 110614](https://github.com/user-attachments/assets/11adedd5-b45f-4c7a-99b9-4fe5d24d9a41)


## Result: 
Thus the python program to detect the lines using Hough Transform was successfully completed.
 
