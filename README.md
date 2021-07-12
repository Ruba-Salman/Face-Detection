# Face-Detection
This task is for make a real face detection.

## 1. Install python and opencv package
```
pip3 install opencv-python
```
## 2. Download the trained classifier
available in: https://github.com/opencv/opencv/tree/master/data/haarcascades
```
import cv2
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
```

## 3. To capture video from webcam
```
cap = cv2.VideoCapture(0)
```
## 4. Call the classifier function
```
_, img = cap.read()
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
faces = face_cascade.detectMultiScale(gray, 1.1, 4)
for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
        cv2.imshow('img', img)
        k = cv2.waitKey(30) & 0xff
    if k==27:
        break
 ```   
## 5. Release the VideoCapture object
 ``` 
cap.release()
 ``` 
