# 🚗 Lane Detection Using OpenCV

This project implements a simple lane detection system using **Canny edge detection**, **image masking**, and the **Hough Line Transform**.

---

## 🔍 Project Overview

- ✅ Reads a road image (`Road.png`)
- ✅ Converts image to grayscale and applies Gaussian blur
- ✅ Detects edges using the Canny Edge Detector
- ✅ Applies a triangular mask to focus on the lane region
- ✅ Uses Hough Line Transform to detect lane lines
- ✅ Draws the detected lines on the original image

---

## 📷 Input & Output

| Input Image | Processed Output |
|-------------|------------------|
| `Road.png`  | Image with overlaid red lane lines |

---

## 🧠 Techniques Used

- `cv2.cvtColor()` for grayscale conversion  
- `cv2.GaussianBlur()` for smoothing  
- `cv2.Canny()` for edge detection  
- `cv2.fillPoly()` for ROI masking  
- `cv2.HoughLinesP()` for detecting straight lines  
- `cv2.line()` and `cv2.addWeighted()` for drawing lines on the image

---

## 💻 How It Works (Code Logic)

Grayscale ➝ Blur ➝ Edge Detection

```python
image = cv2.imread('Road.png')
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blur = cv2.GaussianBlur(gray, (5, 5), 0)
edges = cv2.Canny(blur, 50, 150)
