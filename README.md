# EX-2 Image Acquisition from Web Camera
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:** 26.02.2024
### Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
### Software Used
- Anaconda - Python 3.7
### Algorithm
- Step 1: Import the cv2 and numpy package.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Developed By:NIRAUNJANA GAYATHRI.G.R
- Step 2: Read the Video frame using the cv2.VideoCapture(0)&emsp;&emsp;&emsp;&emsp;&emsp;Register Number: 212222230096
- Step 3: Write the image using imwrite().
- Step 4: Display the frame using the imshow().
- Step 5: Divide the frame into halves and assign the smaller frame
- Step 6: Rotate the frame using the cv2.rotate().
### Program:
<table>
    <tr>
        <td>
            
#### i) Write the frame as JPG file
```Python
import cv2
Obj=cv2.VideoCapture(0)
while (True):
    ret,fr=Obj.read()
    cv2.imwrite("niru.jpg",fr)
    result=True
Obj.release()
cv2.destroyAllWindows()
```
</td>
<td>
    
#### Output:
![image](https://github.com/niraunjana/Image_Acqusition-_using_Web_Camera/assets/119395610/a2c6f541-f3d0-4ed4-ab01-79c1f72171d0)

</td>
</tr>
</table>
<table>
<tr>
        <td>
            
#### ii) Display the video
```Python
import cv2
img=cv2.VideoCapture(0)
while(True):
    image,fr=img.read()
    cv2.imshow('niru212222230096',fr)
    cv2.imwrite("niru.jpg",fr)
    if cv2.waitKey(1) =ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```

</td>
<td>
    
#### Output:<br>
 ![image](https://github.com/niraunjana/Image_Acqusition-_using_Web_Camera/assets/119395610/db51af07-5035-4dd3-bf7d-51cbe6fbf073)

</td>
</tr>

<tr>
    <td>

    
#### iii) Display the video by resizing the window
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,fr=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(fr.shape,np.uint8)
    sfram=cv2.resize(fr,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=sfram
    image[height//2:,:width//2]=sfram
    image[:height//2,width//2:]=sfram
    image[height//2:,width//2:]=sfram
    cv2.imshow('niru212222230096',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
</td>
     <td>

#### Output:<br>
![image](https://github.com/niraunjana/Image_Acqusition-_using_Web_Camera/assets/119395610/4a43aba8-c546-4364-860b-c7cd113c6719)

</td>   
</tr>
<tr>
    <td>
        
#### iv) Rotate and display the video
```Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,fr=cap.read() 
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(fr.shape, np.uint8) 
    sfram=cv2.resize(fr,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=cv2.rotate(sfram,cv2.ROTATE_180)
    image[height//2:,:width//2]=sfram 
    image[:height//2,width//2:]=sfram
    image[height//2:,width//2:]=cv2.rotate(sfram,cv2.ROTATE_180)
    cv2.imshow('niru212222230096',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
</td>
<td>
    
### Output:<br>
 ![image](https://github.com/niraunjana/Image_Acqusition-_using_Web_Camera/assets/119395610/d5a3f9f1-c0cd-4496-846c-cf3860b9fe72)

  </td>
  </tr>
</table>

### Result:
Thus the image is accessed from webcamera and displayed using openCV.
