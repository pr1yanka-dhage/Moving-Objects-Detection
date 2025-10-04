# Motion Detection using OpenCV

## 📘 Overview

This project implements a **real-time motion detection system** using **OpenCV**. It captures video frames from the webcam, processes them, and detects motion by comparing consecutive frames.

---

## ⚙️ Technologies Used

* **Python** 🐍
* **OpenCV** – for image and video processing
* **imutils** – for easier image resizing and contour operations
* **time** – for introducing delays when initializing the camera

---

## 🧠 Working Principle

1. Capture live video feed using `cv2.VideoCapture(0)`.
2. Convert each frame to grayscale and apply **Gaussian Blur** to reduce noise.
3. Compare the first frame with the current frame using `cv2.absdiff()` to detect changes.
4. Apply **binary thresholding** and **dilation** to highlight movement.
5. Find **contours** of the moving objects and draw bounding boxes around them.
6. Display real-time output with labels indicating movement.

---

## 🧩 Key Components

| Component             | Purpose                                              |
| --------------------- | ---------------------------------------------------- |
| `cv2.VideoCapture(0)` | Opens the webcam feed                                |
| `time.sleep(1)`       | Gives camera time to adjust before capturing         |
| `cv2.cvtColor()`      | Converts frame to grayscale                          |
| `cv2.GaussianBlur()`  | Smoothens image and reduces noise                    |
| `cv2.absdiff()`       | Finds absolute difference between frames             |
| `cv2.threshold()`     | Converts image to binary for easier motion detection |
| `cv2.findContours()`  | Detects boundaries of moving objects                 |
| `cv2.rectangle()`     | Draws rectangles around detected motion              |

---

## 🚀 Execution Flow

1. **Initialize camera** and capture first frame as reference.
2. **Continuously capture frames** and compare them with the reference frame.
3. **Detect motion** when pixel difference exceeds a threshold.
4. **Draw rectangles** around moving objects and display the feed.
5. **Exit** the program by pressing the **'q'** key.

---

## 📈 Output Example

* Normal state: "Normal"
* When motion detected: "Moving Object detected"

Bounding boxes appear around moving objects in green color.

---

## 🧹 Notes

* Default motion sensitivity: area > 500 pixels
* Press **'q'** to quit the camera feed window.
* The first frame acts as a static reference background.

---

## 🔧 Possible Enhancements

* Add sound or email alerts when motion is detected.
* Save frames or video when motion occurs.
* Use background subtraction or deep learning for higher accuracy.
* Implement region-of-interest (ROI) for targeted motion tracking.
