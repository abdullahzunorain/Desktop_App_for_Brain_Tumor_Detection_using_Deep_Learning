# Brain Tumor Detection and Visualization System

This project is a **Brain Tumor Detection** system that uses MRI scans to detect and visualize tumors. The application is built using Python with a graphical user interface (GUI) created using `Tkinter`. The system allows users to upload MRI images, detect the presence of tumors, and visualize the tumor region in the image using pre-trained machine learning models and image processing techniques.

## Features

- **Image Upload**: Upload MRI images using a file browser.
- **Tumor Detection**: Automatically detect the presence of brain tumors using a pre-trained model.
- **Tumor Visualization**: View the region of the detected tumor in the MRI image.
- **User-Friendly GUI**: A simple interface to interact with the system and display results.
- **Real-time Results**: Instant feedback on the detection results and visualization of tumor regions.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Working Process](#working-process)
- [Requirements](#requirements)
- [License](#license)

## Installation

To run the Brain Tumor Detection system locally, follow the steps below:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/brain-tumor-detection.git
   cd brain-tumor-detection
   ```

2. **Install Required Libraries**:
   Install the necessary Python packages using `pip`:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application**:
   After installing the dependencies, run the `gui.py` file to start the GUI:
   ```bash
   python gui.py
   ```

## Usage

1. **Browse Image**: Click the `Browse` button to upload an MRI image file (formats supported: `.jpg`, `.png`, `.jpeg`).
2. **Select an Option**:
   - Choose the **Detect Tumor** option to detect whether a tumor is present in the MRI scan.
   - Choose the **View Tumor Region** option to visualize the tumor region on the MRI image.
3. **View Results**:
   - If a tumor is detected, a message will be displayed: "Tumor Detected" (in red) or "No Tumor" (in green).
   - The detected tumor region will be highlighted and displayed on the MRI image.

## Project Structure

The project directory is structured as follows:

```
brain-tumor-detection/
│
├── frames.py              # Handles the GUI frames and image display logic
├── displayTumor.py        # Contains methods for tumor visualization
├── predictTumor.py        # Performs brain tumor prediction
├── gui.py                 # Main file that runs the GUI application
├── README.md              # This README file
├── requirements.txt       # List of required dependencies
└── assets/                # Contains example MRI images (if any)
```

### Key Files:

- **`gui.py`**: The main entry point of the project. Initializes the GUI and manages user interactions.
- **`frames.py`**: Defines the `Frames` class, which manages the GUI frames, image handling, and event bindings.
- **`predictTumor.py`**: Defines the `predictTumor()` function that processes the MRI image and detects the presence of a tumor using a pre-trained machine learning model.
- **`displayTumor.py`**: Implements methods to visualize and highlight tumor regions in MRI images.

## Working Process

### Step 1: Uploading an MRI Image
- The user uploads an MRI image by clicking the **Browse** button, which opens a file dialog to select an image. The selected image is loaded and displayed in the GUI.

### Step 2: Tumor Detection
- The user can select the **Detect Tumor** option to check if the MRI image contains a tumor.
- The `predictTumor()` function (defined in `predictTumor.py`) is called, which uses a machine learning model (e.g., a convolutional neural network) to classify the MRI image as having a tumor or not.
- Based on the prediction, a message "Tumor Detected" (in red) or "No Tumor" (in green) is displayed on the GUI.

### Step 3: Tumor Region Visualization
- If the user selects the **View Tumor Region** option, the system will visualize the tumor region on the MRI image.
- The `DisplayTumor` class (defined in `displayTumor.py`) processes the MRI image by removing noise and highlighting the tumor region.
- The processed image is then displayed on the GUI, allowing the user to see where the tumor is located.

### Step 4: GUI Navigation
- The application uses the `Frames` class (from `frames.py`) to manage different frames (sections of the GUI) and handle image loading, button interactions, and switching between different functionalities (e.g., detection vs. visualization).
- The `NextWindow()` method is used to transition between frames when the user clicks the **View** button to see the next step of processing.

## Requirements

The following dependencies are required to run this project:

- Python 3.9
- Tkinter (for GUI)
- OpenCV (`cv2` for image processing)
- Pillow (`PIL` for image handling)
- Numpy (for handling arrays)
- Pre-trained machine learning model for brain tumor detection (e.g., VGG16, Xception)

To install all required dependencies, run:

```bash
pip install -r requirements.txt
```
