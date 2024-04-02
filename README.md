# Edge-Linking-using-Hough-Transform
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


## Program 

### Developed by : PRAVEEN S
### Reg.No. 212222240078

### Image Processing

```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("vkk.jpeg",0)
img_c=cv2.imread("vkk.jpeg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)

```

```py
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
```
```py
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Canny Edge Detection

```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Hough Transform

```py
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```


## Output

### Input image and grayscale image

![image](https://github.com/Praveen0500/Edge-Linking-using-Hough-Transformm/assets/120218611/d0c12f42-9e40-40dc-962c-c649e36d0d7f)


### Canny Edge detector output


![image](https://github.com/Praveen0500/Edge-Linking-using-Hough-Transformm/assets/120218611/15b0947f-f156-4b40-92b7-8ff1a9738662)



### Display the result of Hough transform

![image](https://github.com/Praveen0500/Edge-Linking-using-Hough-Transformm/assets/120218611/98e8e2fc-8dc6-49e9-8186-b6a114dd945b)


## Result:

### Thus the program is written with python and OpenCV to detect lines using Hough transform.
