#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```python
# Read the image using OpenCV

###
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread(r"C:\Users\sdhan\Downloads\WhatsApp Image 2026-10-17 at 3.09.40 PM.jpeg")  # Replace 'image.jpg' with your image path

###
```

---

###  Step 3: Convert to Grayscale

```python
# Convert to grayscale.

###
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
###
```

---

###  Step 4: Display Images

```python
plt.figure(figsize=(10,5))

###
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
###
```
<img width="295" height="358" alt="image" src="https://github.com/user-attachments/assets/362d9632-135c-40c3-b74f-049fd4e8d277" />


<img width="308" height="352" alt="image" src="https://github.com/user-attachments/assets/e2e23bad-7af0-4ab0-9213-0ec8f46b7468" />

---


### Step 7: Edge Detection (Canny)

```python
# Perform Edge Detection

###
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
###
```
<img width="262" height="360" alt="image" src="https://github.com/user-attachments/assets/0ce530b1-d1f8-40f5-aa43-ffcf8e75c0aa" />

---


###  Step 9: Hough Transform

```python
# Detect lines using Hough Transform

###
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

###
```
<img width="286" height="372" alt="image" src="https://github.com/user-attachments/assets/36b91148-caf0-4c48-bf23-dbb883f9b3b2" />

---



##  Expected Output

* Original image
* Grayscale image
* Edge detected image
* Detected lines
* Final lane detection output


##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs



## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.


##  Developed By

* **Name:** ___DEVI S_________________________
* **Register No:** _212225100008_____________________
