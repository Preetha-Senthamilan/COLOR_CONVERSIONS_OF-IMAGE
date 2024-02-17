# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
Developed by :PREETHA S
Register Number :212222230110

### 1)Read and display the image

```

import cv2
image=cv2.imread('pre.webp',1)
image=cv2.resize(image,(400,300))
cv2.imshow('PREETHA',image)
cv2.waitKey(0)
cv2.destroyAllWindows() 

```
### Output

![Screenshot 2024-02-17 083356](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/696f55f1-26c6-4802-952d-177295efcc2b)

### 2)Write the image
```
import cv2
image=cv2.imread('pre.webp',0)
cv2.imwrite('de.jpg',image)
```
### Output

![Screenshot 2024-02-17 084216](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/059bcad1-447c-4efa-9181-ebe8bed3dd77)

### 3)Shape of the Image
```
import cv2
image=cv2.imread('pre.webp',1)
print(image.shape)
```

## Output

![Screenshot 2024-02-17 084514](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/f29954a1-489e-4094-b706-041dac91749b)

### 4)Access rows and columns
```
    import random
    import cv2
    image=cv2.imread('pre.webp',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
### Output

![Screenshot 2024-02-17 084804](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/8a914ccf-08e9-4981-b4cb-6127a2bb58ab)

### v)Cut and paste portion of image
```
   import cv2
   image=cv2.imread('pre.webp',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
### Output

![Screenshot 2024-02-17 085334](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/8af4591c-7a28-4633-af82-81e6c047007a)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('pre.webp',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output

![Screenshot 2024-02-17 092251](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/f5b176f1-3a06-418b-ad13-cb4f308b2561)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('pre.webp')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output

![Screenshot 2024-02-17 093457](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/81cd0a10-27dc-4aa7-819f-bdd1783409ed)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('pre.webp')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output
![Screenshot 2024-02-17 094627](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/07726224-9aa5-4ae0-8cf3-bd2d311d054f)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('pre.webp',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output

![Screenshot 2024-02-17 100242](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/252794a7-b292-40a5-a52e-106033ece53c)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("pre.webp",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output

![Screenshot 2024-02-17 100610](https://github.com/Preetha-Senthamilan/COLOR_CONVERSIONS_OF-IMAGE/assets/119390282/46f0f58e-24d5-4a27-850d-10a711b93821)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







