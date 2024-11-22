# Ex-1-COLOR_CONVERSIONS_OF-IMAGE
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
### Developed By: Pravin kumar G
### Register Number: 212222230109


## i)Read and Display an Image
### Program:

```python
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
## Output:
![image](https://github.com/user-attachments/assets/60780b34-6a32-45f2-a036-4569da419421)


## ii)Draw Shapes and Add Text
### Program:

```python
import cv2

# Load the image
img = cv2.imread("Lokesh.JPG")

# Image dimensions
height, width = img.shape[:2]

# 1. Draw a line from top-left to bottom-right
line_img = img.copy()
cv2.line(line_img, (0, 0), (width, height), (0, 255, 0), 10)
cv2.imshow('Line', line_img)
cv2.imwrite('Line_Image.jpg', line_img)
cv2.waitKey(0)

# 2. Draw a circle at the center
circle_img = img.copy()
cv2.circle(circle_img, (width//2, height//2), 150, (255, 0, 0), 10)
cv2.imshow('Circle', circle_img)
cv2.imwrite('Circle_Image.jpg', circle_img)
cv2.waitKey(0)

# 3. Draw a rectangle around the entire image
rectangle_img = img.copy()
cv2.rectangle(rectangle_img, (0, 0), (width, height), (100, 255, 100), 10)
cv2.imshow('Rectangle', rectangle_img)
cv2.imwrite('Rectangle_Image.jpg', rectangle_img)
cv2.waitKey(0)

# 4. Add text at the top-left corner
text_img = img.copy()
text = "OpenCV Drawing"
org = (10, 30)
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
text_color = (255, 255, 255)
thickness = 2
cv2.putText(text_img, text, org, font, font_scale, text_color, thickness, cv2.LINE_AA)
cv2.imshow('Text', text_img)
cv2.imwrite('Text_Image.jpg', text_img)
cv2.waitKey(0)

# Clean up windows
cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/user-attachments/assets/16118472-94c2-4c95-b4bd-739a2f58b253)


![image](https://github.com/user-attachments/assets/2105c5cd-e5ea-4e0f-aeb4-b37d097e789c)


![image](https://github.com/user-attachments/assets/35db45a3-e521-4128-a597-ee8ef4119f29)


![image](https://github.com/user-attachments/assets/da7fbc43-7140-4000-b87d-aa7498fafb38)



## iii)Image Color Conversion
### Program:

```python
import cv2

# Read the image
image = cv2.imread("Lokesh.JPG")

# Convert to HSV color space
img_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
cv2.imshow('Image Window (HSV)', img_hsv)
cv2.imwrite('Lokesh_HSV.jpg', img_hsv)  # Save HSV image
cv2.waitKey(0)

# Convert to grayscale
img_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
cv2.imshow('Grayscale Image', img_gray)
cv2.imwrite('Lokesh_Gray.jpg', img_gray)  # Save grayscale image
cv2.waitKey(0)

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.imwrite('Lokesh_YCrCb.jpg', ycrcb_image)  # Save YCrCb image
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.imwrite('Lokesh_HSV_to_RGB.jpg', hsv_to_rgb_image)  # Save the converted RGB image
cv2.waitKey(0)

# Clean up
cv2.destroyAllWindows()
```
## Output:
### Convert the image from RGB to HSV and display it:
![image](https://github.com/user-attachments/assets/14f94f43-5d4b-4d42-81fd-1d9ec2e00982)

### Convert the image from RGB to GRAY and display it:
![image](https://github.com/user-attachments/assets/5ce97210-4fac-4a63-98bf-565901fb5c49)

### Convert the image from RGB to YCrCb and display it:
![image](https://github.com/user-attachments/assets/348d7ab1-d6d7-4c4f-b24c-5aa0afa74880)

### Convert the HSV image back to RGB and display it:
![image](https://github.com/user-attachments/assets/627ac673-08df-40ba-b08d-7606cf014a16)


## iv)Access and Manipulate Image Pixels
### Program:

```python
import cv2
image = cv2.imread('Lokesh.jpg')
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")
# Modify the color of the pixel at (200, 200) to white (255, 255, 255)
image[200, 200] = [255, 255, 255]
# Find and print the modified pixel value
modified_pixel_value = image[200, 200]
print(f"Modified pixel value at (200, 200): {modified_pixel_value}")
# Save the modified image
cv2.imwrite('modified_image.jpg', image)
```
## Output:
![Screenshot 2024-09-25 091415](https://github.com/user-attachments/assets/ce6bf38b-0d10-4b67-9def-a4a40e374c0e)


## v)Image Resizing
### Program:

```python
# Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
## Output:
![image](https://github.com/user-attachments/assets/feb6684c-ff46-4c33-9a2f-76223c7c50cb)

<br>
<br>

## vi)Image Cropping:
### Program:

```python
# Image Cropping
# Check if the image was loaded successfully
if image is None:
    print("Error: The image file could not be loaded. Check the file path and format.")
else:
    # Crop a region of interest (100x100 pixels starting at (50, 50))
    roi = image[50:150, 50:150]
    # Display the cropped image
    cv2.imshow('Cropped ROI Image', roi)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
    # Optionally, save the cropped image
    cv2.imwrite('cropped_image.jpg', roi)
```
## Output:

![image](https://github.com/user-attachments/assets/6cf6657e-eedb-4042-96c2-a51bc05618df)


## vii)Image Flipping
### Program:

```python
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
## Output:
![image](https://github.com/user-attachments/assets/5131d0f9-ace7-47d2-b5a4-752a5b6dcf96)

### Flip the original image vertically and display it:
## Output:
![image](https://github.com/user-attachments/assets/64dfe874-a6e4-4066-8535-4132c721bb38)


## viii)Write and Save the Modified Image
### Program:

```python
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
## Output:
![image](https://github.com/user-attachments/assets/e771e2d7-3471-485e-a925-47fc72049848)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







