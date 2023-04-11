# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it a image variable.

### Step2:
Create a transformation matrix and apply a perspective transformation to the image amd display the resulting image.

### Step3:
Similarly Create a perspective matrix for scaling the image and using the appropriate function display the scaled image

### Step4:
Specify the angle of rotation in radians for displaying rotated image and display it.

### Step5:
End the execution.

## Program:
```
Developed By: M.Suwetha
Register Number: 212221230112

Reading the image : 

import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("d7.jpeg")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim = input_image.shape

i)Image Translation:

M = np.float32([[1,0,200],[0,1,100],[0,0,1]])
trans_image = cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(trans_image)
plt.show()


ii) Image Scaling:

M = np.float32([[1.5,0,0],[0,0.8,0],[0,0,1]])
scaled_image = cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_image)

iii)Image shearing:

M_x = np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
M_y = np.float32([[1,0,0],[0.5,1,0],[0,0,1]])
sheared_image_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols*1.5),(int(rows*1.5))))
sheared_image_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols*1.5),(int(rows*1.5))))
plt.imshow(sheared_image_xaxis)
plt.imshow(sheared_image_yaxis)

iv)Image Reflection

M_x = np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
M_y = np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
ref_image_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols),(int(rows))))
ref_image_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols),(int(rows))))
plt.imshow(ref_image_xaxis)
plt.imshow(ref_image_yaxis)

v)Image Rotation

angle = np.radians(90)
M = np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
rot_img = cv2.warpPerspective(input_image,M_x,(int(cols),(int(rows))))
plt.imshow(rot_img)

```
## Output:
### i)Image Translation

![i-1](https://user-images.githubusercontent.com/94165336/231249318-61f4ceee-fd5f-4bf4-882c-9091512491ef.png)

### ii) Image Scaling


### iii)Image shearing

![i-3](https://user-images.githubusercontent.com/94165336/231249658-d65a238e-c443-4258-9426-dae0f6d43b3a.png)


### iv)Image Reflection

![i-4](https://user-images.githubusercontent.com/94165336/231249772-3599b4a4-8075-4ee0-8dbe-d551aa1f1a8c.png)


### v)Image Rotation

![i-5](https://user-images.githubusercontent.com/94165336/231249925-44124990-f78f-4faf-b160-c6b5055a4b41.png)


### vi)Image Cropping

![i-6](https://user-images.githubusercontent.com/94165336/231250027-1be6be11-6377-41bd-bf40-04e6960a7b98.png)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
