# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: pravin kumar G
### Register Number: 212222230109


## Output:

### i)Read and Display an Image

```
import cv2
# Read the image
image = cv2.imread('Lokesh.JPG')
# Display the image in a window
cv2.imshow('Image Window', image)
# Wait indefinitely for a key press
cv2.waitKey(0)
# Destroy all windows created by OpenCV
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/f21cc1d1-82f1-48c5-a35b-e4adbe02580d)
<br>
<br>

### ii)Draw Shapes and Add Text

```
import cv2

img = cv2.imread("Lokesh.JPG")
start=(0,0)
stop=(500,329)
color=(100,255,100)
thickness=10
res_img=cv2.circle(img,(330,225),150,(255,0,0),10)
res_img=cv2.rectangle(img,start,stop,color,thickness)
text = "OpenCV Drawing"
org = (10, 30)  # top-left corner of the text string
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
text_color = (255, 255, 255)  # White color
thickness = 2
res_img = cv2.line(img,(100,200),(900,100),(200,100,205),10)
res_img= cv2.putText(res_img, text, org, font, font_scale, text_color, thickness, cv2.LINE_AA)

# Display the HSV image
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/4b8f523c-b59a-4170-83b6-1ce21605a86e)
![image](https://github.com/user-attachments/assets/2a6a9d91-84a1-492c-9fdf-9ca5d125ee45)
![image](https://github.com/user-attachments/assets/f3d901d2-1ff0-482b-aaef-7e54230f1696)
![image](https://github.com/user-attachments/assets/7712f3fe-3d30-4c09-8813-3c869de1f7a4)



<br>
<br>

### iii)Image Color Conversion

```
# Read the image
image = cv2.imread("Lokesh.JPG")

# Convert to HSV color space
img_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
# Convert to grayscale
img = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Display the HSV image
cv2.imshow('Image Window (HSV)', img_hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.waitKey(0)
```
### Convert the image from RGB to HSV and display it:
![image](https://github.com/user-attachments/assets/c6b5d1d6-a215-489f-b52a-71d66129309f)

### Convert the image from RGB to GRAY and display it:
![image](https://github.com/user-attachments/assets/f9a8df5e-3afe-4ff1-8185-1c161a1cf51e)

### Convert the image from RGB to YCrCb and display it:
![image](https://github.com/user-attachments/assets/219bb116-72e7-43b6-af84-28f92982bb7e)

### Convert the HSV image back to RGB and display it:
![image](https://github.com/user-attachments/assets/96eecc60-c49e-47b3-bf91-ac29f5b575fd)

<br>
<br>

### iv)Access and Manipulate Image Pixels

```
# Step 4: Access and Manipulate Image Pixels
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the color of the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]
print(f"Modified pixel value at (200, 200): {image[200, 200]}")
```
![image](https://github.com/user-attachments/assets/66bf0b1a-3b5a-4da3-a159-90b507f5eeed)
<br>
<br>

### v)Image Resizing
```
# Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/56c20463-efc2-4869-b6a3-e50fda8cc4fa)

<br>
<br>

### vi)Image Cropping:

```
# Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/c9f1404f-7951-4326-bc1b-efa8acb57da6)

<br>
<br>

### vii)Image Flipping

```
# Flip the original image horizontally and display it
flipped_horizontally = cv2.flip(image, 1)
cv2.imshow('Horizontally Flipped Image', flipped_horizontally)
cv2.waitKey(0)

# Flip the original image vertically and display it
flipped_vertically = cv2.flip(image, 0)
cv2.imshow('Vertically Flipped Image', flipped_vertically)
cv2.waitKey(0)
```

### Flip the original image horizontally and display it:
![image](https://github.com/user-attachments/assets/afc3e98b-15ef-4188-a3c9-b281eeae8db6)

### Flip the original image vertically and display it:
![image](https://github.com/user-attachments/assets/07e2be4b-5245-4cc6-aa72-05e060659bc4)

<br>
<br>

### viii)Write and Save the Modified Image

```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
![image](https://github.com/user-attachments/assets/6067a52f-78b8-464b-a93c-b15960bb302d)
<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







