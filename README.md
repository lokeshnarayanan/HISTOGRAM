# HISTOGRAM
# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:Load the image using a suitable library like OpenCV.
<br>

### Step2:Convert the image to grayscale using cvtColor() if needed.
<br>

### Step3:Calculate the histogram using calcHist() and plot it with Matplotlib.
<br>

### Step4:Perform histogram equalization using equalizeHist() for enhanced contrast.


<br>

### Step5:Visualize results by plotting histograms and displaying original and equalized images side by side.
<br>

## Program:
```python
# Developed By:Lokesh N
# Register Number:212222100023
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image_path = 'grey.png'
gray_image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)
hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(hist)
plt.xlabel('Pixel Value')
plt.ylabel('Frequency')
plt.title('Histogram of Grayscale Image')
plt.show()
```
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image_path = 'moon.png'
color_image = cv2.imread(image_path, cv2.IMREAD_COLOR)
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)
hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(hist)
plt.xlabel('Pixel Value')
plt.ylabel('Frequency')
plt.title('Histogram of color Image')
plt.show()
```



# Display the histogram of gray scale image and any one channel histogram from color image
```python
import numpy as np
import cv2
Gray_image = cv2.imread("moon.png")
Color_image = cv2.imread("grey.png")
import matplotlib.pyplot as plt
gray_hist = cv2.calcHist([Gray_image],[0],None,[256],[0,256])
color_hist = cv2.calcHist([Color_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(Gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(Color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()
cv2.waitKey(0)
cv2.destroyAllWindows()

```

# Write the code to perform histogram equalization of the image. 

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image_path = 'moon.png'
gray_image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)
equalized_image = cv2.equalizeHist(gray_image)
hist_before = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
hist_after = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.figure(figsize=(10, 6))
plt.subplot(2, 1, 1)
plt.plot(hist_before)
plt.title('Original Histogram')
plt.xlabel('Pixel Value')
plt.ylabel('Frequency')
plt.subplot(2, 1, 2)
plt.plot(hist_after)
plt.title('Equalized Histogram')
plt.xlabel('Pixel Value')
plt.ylabel('Frequency')
plt.tight_layout()
plt.show()
cv2.imshow('Original Grayscale Image', gray_image)
cv2.imshow('Equalized Grayscale Image', equalized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:

# Input Grayscale Image and Color Image
![grey](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/695da950-4ad3-45d2-8016-b39166334120)
![moon](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/2f433796-fd6d-4778-adaf-e3062a17a1fd)
![Equalized Grayscale Image_screenshot_30 08 2023p](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/2d4fd50f-4723-43eb-ad32-b279db1f1103)

# Histogram of Grayscale Image and any channel of Color Image
![Screenshot from 2023-08-30 14-01-00](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/5d61cc01-f520-4c36-8790-61651f805fc7)
![Screenshot from 2023-08-30 14-01-53](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/90c5af2e-84c6-4c8b-ad71-e0734bfd422a)
![Screenshot from 2023-08-30 14-05-21](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/3dc322a8-d693-41e9-864f-4133754f4d84)
![Screenshot from 2023-08-30 14-20-52](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/6a443dc8-60c5-4662-aae4-f1a4ca744362)
![Screenshot from 2023-08-30 14-15-12](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/a7a37a20-0a01-4d2f-8aa1-1ad69f126821)




# Histogram Equalization of Grayscale Image
![Screenshot from 2023-08-30 13-57-40](https://github.com/lokeshnarayanan/HISTOGRAM/assets/119393019/809d4def-17bf-48b0-b997-504ab78be5c4)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
