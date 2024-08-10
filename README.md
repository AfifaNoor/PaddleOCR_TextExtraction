
# PaddleOCR Bounding Box Detection and Text Extraction

This repository provides a Python script that utilizes PaddleOCR to detect text within an image, generate bounding boxes around the detected text, and save the results in a JSON format. The repository also includes instructions for setting up a Python virtual environment and installing PaddleOCR.

## Features

- **Text Detection and Extraction**: Detects text from images and extracts both the text and its corresponding bounding box coordinates.
- **JSON Output**: Saves the bounding box coordinates, detected text, and confidence scores to a JSON file.
- **Bounding Box Visualization**: Draws bounding boxes around detected text on the image and saves the output image.

## Prerequisites

- **Operating System**: The code is compatible with Linux or server environments. It may not work properly on Windows due to environment-specific issues.
- **Python Version**: Python 3.7 or higher is recommended.

## Installation and Setup

To set up the environment and install the necessary dependencies, follow these steps:

### 1. Create a Python Virtual Environment

First, create a new Python virtual environment:

```bash
python -m venv newenv
```

### 2. Activate the Virtual Environment

Activate the virtual environment:

- **Linux/Server**:
  ```bash
  source newenv/bin/activate
  ```

- **Windows** (Not recommended):
  ```bash
  newenv\Scripts\activate
  ```

### 3. Upgrade pip

Upgrade pip to the latest version:

```bash
pip install --upgrade pip
```

### 4. Install PaddlePaddle

Install PaddlePaddle based on your hardware configuration:

- **CPU**:
  ```bash
  pip install paddlepaddle==2.6.1 -c https://paddlepaddle.org.cn/whl/cpu/avx/stable.html
  ```

- **GPU**:
  ```bash
  pip install paddlepaddle-gpu==2.6.1 -f https://paddlepaddle.org.cn/whl/cuda112/stable.html
  ```

### 5. Install PaddleOCR

Install PaddleOCR version 2.8.1:

```bash
pip install paddleocr==2.8.1
```

## Code Explanation

The `get_coords_and_text` function in the provided script performs the following tasks:

1. **Initialization**: 
   - The PaddleOCR model is initialized with English language support and angle classification enabled.

2. **Image Reading**:
   - The image is read using OpenCV. If the image fails to load, an error is raised.

3. **OCR Processing**:
   - The image is processed using PaddleOCR to detect text. The result is printed for debugging and saved in a raw JSON file.

4. **Bounding Box Extraction**:
   - The detected text's bounding box coordinates are extracted, converted to integer format, and stored along with the text and confidence score in a dictionary.

5. **Bounding Box Visualization**:
   - Bounding boxes are drawn on the original image using OpenCV, and the image is saved.

6. **JSON Output**:
   - The processed bounding box and text information are saved in a JSON file.

## Running the Code

After setting up the environment and installing the dependencies, you can run the script using the following command:

```python

Replace `your_script_name.py` with the name of the script provided in this repository.

Make sure to specify the correct image path and output paths for the JSON files in the script.

## Important Notes

- **Environment Compatibility**: The code is designed to run in Linux or server environments. It may not function correctly on Windows due to specific issues with PaddlePaddle or PaddleOCR on this OS.
- **Dependencies**: Ensure that you are using the correct versions of PaddlePaddle and PaddleOCR as specified in the installation steps.

## Example Usage

Here is an example of how to call the `get_coords_and_text` function:

```python
image_path = r"/path/to/your/image.png"
output_json_path = r"/path/to/save/Paddleocr_result.json"
raw_ocr_json_path = r"/path/to/save/raw_ocr_result.json"

get_coords_and_text(image_path, output_json_path, raw_ocr_json_path)
```

This will process the image at the specified `image_path`, draw bounding boxes on the detected text, and save the processed data and raw OCR result as JSON files.

---

This README file includes all the necessary instructions, explanations, and notes to help users understand the purpose of the code, how to set up the environment, and how to run the code.
