# Barcode-Detector-And-Decoder
Python code for detecting, localizing, and decoding barcodes using the OpenCV library.
# Barcode Detector and Decoder

A Python script for detection, extraction, and decoding barcodes from images. The system processes images from a designated folder, compares the decoded output against ground-truth solutions, and evaluates overall accuracy.

## Dataset
The dataset used for testing and developing this project can be found here (dataset1 used): 
[Link to Dataset] https://artelab.dista.uninsubria.it/downloads/datasets/barcode/medium_barcode_1d/medium_barcode_1d.html 

## Important Note
For the program to run successfully, ensure that **both the Python script and the dataset files are located in the same folder/directory**.

## Methods & Processing Pipeline
The application relies on several image processing and computer vision techniques implemented via OpenCV:
* **Image Preprocessing:** Preprocessing the image using Gaussian blur and morphological closing operations to suppress noise, while masking non-white and non-black pixels to enhance efficiency.
* **Barcode Localization & Rectification:** Detecting rectangular contours to isolate the barcode region, followed by automatic rotation alignment based on line detection and angle calculation to ensure the barcode is horizontal and correctly oriented.
* **Text Removal:** Identifying and masking surrounding numbers and text by locating specific contour height distributions and filling them with white blocks.
* **Binarization & Decoding:** Converting the processed image into a binary string representation, parsing start/stop markers and center patterns, and applying parity schemes (EAN-13 standard logic) to decode individual digits and reconstruct the final product code.

## Performance & Future Improvements
* **Current Baseline Accuracy:** ~12.21% across the test dataset.
* **Note on Accuracy:** This is an experimental prototype. Performance can be significantly enhanced by fine-tuning filter parameters, image transformations, and handling non-ideal conditions (such as crumpled or distorted barcodes). Future iterations aim to improve barcode localization by detecting multiple parallel rectangular contours instead of relying solely on single outer-rectangle bounding.

## Tech Stack
* Python
* OpenCV

## How to Run
1. Install the required dependencies:
   ```bash
   pip install opencv-python
