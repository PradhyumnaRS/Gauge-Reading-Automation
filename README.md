# Computer Vision Based Meter Reading & Validation (IISc Internship)

This repository contains the end-to-end computer vision pipeline developed during my research internship at the **Indian Institute of Science (IISc)**. The project automates data extraction from both Digital and Analog industrial meters using Deep Learning and Geometric Analysis.

##  Project Overview
Manual data logging in industrial environments is prone to error and time-consuming. This project provides a dual-pipeline solution to digitize flow rates (SLPM/Nm³/h) in real-time from high-definition video feeds and static images.

### Key Technical Components:
* **Digital Pipeline:** Leverages **EasyOCR** (built on **PyTorch**) to detect LCD segments and extract numeric values.
* **Analog Pipeline:** Uses **OpenCV** for pivot-point detection and angular geometry to map needle positions to metric values.
* **Performance:** Optimized for low-latency inference using **CUDA** acceleration on an NVIDIA RTX 3050 Ti.

---

## Deep Learning Stack & Torchvision
The project utilizes the **PyTorch** ecosystem for robust optical character recognition and image processing:
* **PyTorch:** Serves as the primary deep learning backend for the OCR models.
* **Torchvision:** Used for essential image transformations, including tensor conversion and normalization, ensuring that frames captured from industrial cameras are in the optimal format for the underlying neural networks.
* **Hardware Acceleration:** Configured to leverage **CUDA cores** on the ROG Strix G15, significantly reducing processing time per frame.

---

## Performance & Validation
A core part of this project was the rigorous validation of the Digital Meter OCR pipeline against manual ground-truth data.

| Metric | Result |
| :--- | :--- |
| **Total Frames Validated** | 1,828 |
| **Exact Match Accuracy** | **70.62%** |
| **Within Margin Accuracy** | **73.19%** |

*Detailed validation logs can be found in `data/digital_validation_results.csv`.*

---

##  Installation & Requirements
To run this project, ensure you have an environment with Python 3.11+ and the following dependencies.

### CUDA Support (Recommended)
To enable GPU acceleration for the OCR models, install PyTorch with the appropriate CUDA toolkit:
```bash
pip install torch torchvision torchaudio --index-url [https://download.pytorch.org/whl/cu118](https://download.pytorch.org/whl/cu118)
