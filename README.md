# programming-challenge

import cv2
import numpy as np

# image read
img =cv2.imread('Downloads/pbl.jpg')   

# image convert it to grayscale
gray = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY) 

# Find the maximum and minimum value 
cv2.minMaxLoc(gray)
max_a =cv2.minMaxLoc(gray)[3][0]
max_b =cv2.minMaxLoc(gray)[3][1] 

x=25
cd1=(max_a+x,max_b+x)
cd2=(max_a-x,max_b-x)
color =(255,0,0)

# finding brightest point
y =5
brightest_point=np.copy(gray)
brightest_point=cv2.rectangle(brightest_point,cd1,cd2,color,y)

# showing image
cv2.imshow("Result",gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
