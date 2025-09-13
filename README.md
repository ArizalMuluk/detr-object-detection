# Advanced Object Tracking & Counting with DETR and SORT

![Project Demo GIF](output_video_final_zone-ezgif.com-resize.gif)

*Ganti `demo.gif` dengan nama file GIF Anda setelah diunggah ke repository ini.*

## 📋 Project Overview

This project demonstrates an advanced computer vision pipeline that goes beyond simple detection to perform robust **object tracking and cumulative counting**. The solution is designed for real-world applications like traffic analysis, retail footfall counting, and security monitoring.

The system processes a video feed to identify objects, assigns a unique ID to each one, and tracks them across frames. A virtual "counting zone" is established to provide an accurate, cumulative total for each object category (`car`, `person`, etc.) only when an object crosses it.

This repository serves as a portfolio piece showcasing skills in modern AI models and the implementation of practical, real-world application logic.

## ✨ Key Features

- **High-Accuracy Detection:** Utilizes the official **Facebook (Meta AI) DETR** model for precise object detection.
- **Unique Object Tracking:** Implements the **SORT (Simple Online and Realtime Tracking)** algorithm to assign and maintain a unique ID for each object.
- **Cumulative Counting:** Provides an accurate total count of unique objects that pass through a designated zone, not just a per-frame count.
- **Real-Time Visualization:** Overlays bounding boxes, unique IDs, the counting zone, and a live total count directly onto the video output.

## 🛠️ Tech Stack

- **Language:** Python
- **Core Libraries:** PyTorch, Hugging Face `transformers`, OpenCV
- **Tracking Algorithm:** SORT (from the original implementation)
- **Dependencies:** NumPy, FilterPy, Scikit-Image
- **Environment:** Developed in a Kaggle Notebook with GPU acceleration.

## ⚙️ Setup and Installation

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [[https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)](https://github.com/ArizalMuluk/detr-object-detection.git)
    cd detr-object-detection
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install transformers timm opencv-python filterpy scikit-image torch
    ```

4.  **Download the SORT tracker code:**
    The SORT algorithm is used directly from the author's source file.
    ```bash
    wget [https://raw.githubusercontent.com/abewley/sort/master/sort.py](https://raw.githubusercontent.com/abewley/sort/master/sort.py)
    ```

## 🚀 Usage

1.  Place your input video file (e.g., `input.mp4`) in the root directory of the project.
2.  Open the `.ipynb` notebook file in a Jupyter environment (like Jupyter Lab or VS Code).
3.  In the main video processing cell, update the `input_video_path` variable to point to your video file:
    ```python
    input_video_path = 'input.mp4'
    ```
4.  Run all the cells in the notebook.
5.  The processed video, `output_video_final_zone.mp4`, will be saved in the project's root directory.

## 📈 Results & Limitations

This system successfully demonstrates the core methodology of combining a state-of-the-art detector with a classic tracking algorithm to create a functional counting application.

As a baseline model, its counting accuracy is robust but can be affected by challenging scenarios with significant **object occlusion** (where objects block each other from the camera's view). This project serves as a strong foundation for developing more advanced, production-ready analytics solutions with refined logic for such edge cases.

## 🙏 Credits & Acknowledgements

-   **Pre-trained Model:** The object detection capability is powered by the [**DETR (DEtection TRansformer)**](https://huggingface.co/facebook/detr-resnet-50) model developed by Facebook AI (Meta AI).
-   **Test Video:** The sample video used for development is provided by **George Morina** from Pexels. [**Link to video**](https://www.pexels.com/video/riding-a-double-decker-bus-5402016/).
-   **Tracking Algorithm:** This project uses the original implementation of the [**SORT algorithm by Alex Bewley**](https://github.com/abewley/sort).
