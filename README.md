# Digital Image Processing – Image to Pencil Sketch Converter

## Overview

This project is a Digital Image Processing application that converts a colored image into a realistic pencil sketch using Python and OpenCV. The implementation demonstrates several fundamental image processing techniques including grayscale conversion, image inversion, Gaussian blurring, and image blending through division.

The project was developed in Google Colab and uses OpenCV, NumPy, and Matplotlib for image processing and visualization.

---

## Features

* Upload images directly from your computer using Google Colab.
* Convert a color image to grayscale.
* Apply image inversion.
* Perform Gaussian blur smoothing.
* Generate a pencil sketch effect.
* Display all intermediate processing stages.
* Save the final sketch image automatically.

---

## Technologies Used

* Python
* OpenCV
* NumPy
* Matplotlib
* Google Colab

---

## Installation

Install the required libraries:

```bash
pip install opencv-python matplotlib numpy
```

---

## Project Workflow

### 1. Upload Image

The user uploads an image from their local computer using the Google Colab file upload utility.

### 2. Read Image

The image is loaded using OpenCV:

```python
original_image = cv2.imread(image_path)
```

### 3. Convert to Grayscale

The color image is transformed into a grayscale image to simplify processing.

### 4. Invert the Grayscale Image

Each pixel value is inverted:

```python
inverted_gray = 255 - gray_image
```

### 5. Apply Gaussian Blur

A Gaussian Blur is applied to smooth the inverted image and reduce details.

```python
blurred = cv2.GaussianBlur(inverted_gray, (21,21), 0)
```

### 6. Invert the Blurred Image

The blurred image is inverted again.

```python
inverted_blur = 255 - blurred
```

### 7. Create Pencil Sketch

The grayscale image is divided by the inverted blurred image to create the sketch effect.

```python
pencil_sketch = cv2.divide(gray_image, inverted_blur, scale=256.0)
```

### 8. Save Output

The generated sketch is saved as:

```python
pencil_sketch.jpg
```

---

## Image Processing Pipeline

Color Image

↓

Grayscale Conversion

↓

Image Inversion

↓

Gaussian Blur

↓

Invert Blurred Image

↓

Division Blending

↓

Pencil Sketch Output

---

## Output

The program displays:

* Original Image
* Grayscale Image
* Inverted Grayscale Image
* Blurred Image
* Inverted Blurred Image
* Final Pencil Sketch

The final output is also saved as:

```text
pencil_sketch.jpg
```

---

## Learning Outcomes

This project demonstrates important Digital Image Processing concepts:

* Image Representation
* Grayscale Transformation
* Image Negatives
* Gaussian Filtering
* Edge Enhancement
* Image Blending
* Computer Vision Fundamentals

---

## Future Improvements

* Adjustable sketch intensity.
* Real-time webcam sketch generation.
* Graphical User Interface (GUI).
* Multiple artistic sketch styles.
* Colored pencil sketch generation.
* Batch processing of multiple images.


