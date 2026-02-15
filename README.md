# Computer Vision Based Meter Reading & Validation (IISc Internship)

This repository contains the work developed during my internship at the **Indian Institute of Science (IISc)**. The project focuses on automating data extraction from both Digital and Analog industrial meters using Computer Vision.

## Project Overview
The goal was to create a robust pipeline that could replace manual data logging. The system processes video/image feeds to detect meter screens or needles and outputs real-time flow rates (SLPM/Nm³/h).

### Key Features:
* **Digital Meter:** Uses EasyOCR and screen detection to extract numeric SLPM values from video frames.
* **Analog Meter:** Implements pivot-point detection and angular geometry to calculate readings based on needle position.
* **Validation:** Includes a comparative analysis between automated readings and manual "ground-truth" data.

---

## Performance & Validation

### Digital Meter Accuracy
The digital pipeline was validated against a manual dataset of **1,828 frames**.
* **Exact Match Accuracy:** 70.62%
* **Margin-of-Error Success:** 73.19% (within acceptable deviation)



### Challenges Addressed:
* **Preprocessing:** Implemented Grayscale and Thresholding filters to handle glare on digital screens.
* **Error Analysis:** Identified that accuracy drops significantly during rapid flow changes or high motion blur, providing a baseline for future optimization.

---

##  Tech Stack
* **Language:** Python
* **Computer Vision:** OpenCV (cv2)
* **OCR:** EasyOCR
* **Data Handling:** Pandas, NumPy

---

##  File Description
* `digital_meter_pipeline.ipynb`: Core logic for screen detection, OCR, and SLPM calculation.
* `analog_needle_detection.ipynb`: Final program for pivot-coordinate mapping and needle angle calculation.
* `digital_validation_results.csv`: The merged results comparing manual entries vs. program identification.

## How to Use
1. Clone the repository.
2. Ensure `easyocr` and `opencv-python` are installed.
3. Update the `image_path` or `video_path` in the notebooks to point to your local files.
