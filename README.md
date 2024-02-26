# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the viedo using cv2.ViedoCapture(0).
### Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).
### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).
### Step 4:
Display the image until the loop gets over.
### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).
## Program:
``` Python

### Developed By:PAVANA.G
### Register No:212222230105

## i) Write the frame as JPG file

import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("pavana.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('shinchan',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230105_pavana',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230105_pavana',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![dipt](https://github.com/gpavana/Image_Acqusition-_using_Web_Camera/assets/118787343/435b57e7-b334-49ba-989b-5cb29e00c0ab)

### ii) Display the video
![WhatsApp Image 2024-02-23 at 11 34 28_6f554b9a](https://github.com/gpavana/Image_Acqusition-_using_Web_Camera/assets/118787343/2f0a9fdf-3417-4e0f-a090-3e2dac1bb47c)

### iii) Display the video by resizing the window
![WhatsApp Image 2024-02-23 at 11 36 17_78d74f29](https://github.com/gpavana/Image_Acqusition-_using_Web_Camera/assets/118787343/d2735903-3f3d-4f33-b422-fb0682409e52)

### iv) Rotate and display the video
![WhatsApp Image 2024-02-23 at 11 37 46_92c550b5](https://github.com/gpavana/Image_Acqusition-_using_Web_Camera/assets/118787343/cdc6b469-9cad-4a81-9b38-fc97431249b2)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
