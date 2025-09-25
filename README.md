
# Image_Acqusition-_using_Web_Camera
# Name: Dhinesh M
# Reg no: 212223040040
## Aim:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
Developed by : Dhinesh M
Reg no:212223040040


## i) Write the frame as JPG file
```
import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window

```
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video



```
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()






```
## Output

### i) Write the frame as JPG image
<img width="935" height="665" alt="image" src="https://github.com/user-attachments/assets/3816e46d-58a9-49bb-893e-1ed57274b614" />



### ii) Display the video
<img width="817" height="460" alt="image" src="https://github.com/user-attachments/assets/8442682d-0351-4369-90d9-2674e5769676" />



### iii) Display the video by resizing the window
<img width="477" height="275" alt="image" src="https://github.com/user-attachments/assets/e4bd8dfe-c60b-4c2c-ac7b-1bc066d81550" />




### iv) Rotate and display the video
<img width="458" height="259" alt="image" src="https://github.com/user-attachments/assets/82074b17-602f-42b9-86f2-694e2b56d86a" />






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
