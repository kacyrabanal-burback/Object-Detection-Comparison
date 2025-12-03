# Computer Vision Algorithm Comparison: YOLOv8 vs Faster R-CNN

## Project Overview
This project compares the performance of two distinct deep learning object detection algorithms: **YOLOv8** (You Only Look Once) and **Faster R-CNN** (Region-based Convolutional Neural Networks). This project uses the algorithms to evaluate the trade-offs between inference speed and detection sensitivity. 

Additionally, **Canny Edge Detection** was used to analyze the structural complexity ("Edge Density") of the images to determine if visual "busyness" correlates with object detection success as the non-deep learning approach.

## Repository Structure
* `KRabanal_TakeHome_Code.ipynb`: The Jupyter Notebook containing the source code, execution loops, and printed output visualizations.
* `README.md`: Project documentation and analysis.

## The Data
The analysis was performed on 10 images taken from **San Diego, California** (e.g., Belmont Park, Scripps Pier, Downtown, Balboa Park). These images were selected to represent various scene types:
* **Crowded Scenes:** Belmont Park, SR-163 Traffic.
* **Natural Landscapes:** Flower Fields, Sunset Cliffs, Birds, Zoo, Balboa Park, Scripps Pier.
* **Urban/Architecture:** Chicano Park, Downtown Views, Boats in Harbor.

## Dependencies
To run this notebook locally, the following libraries are required:
* `ultralytics` (YOLO implementation)
* `torch` & `torchvision` (Faster R-CNN implementation)
* `opencv-python` (cv2)
* `pandas`

## Key Findings
### 1. Speed vs. Accuracy Trade-off
* **YOLOv8 (Nano)** demonstrated superior speed, suitable for real-time applications. The inference time ranged between **0.17s and 0.39s** per image.
* **Faster R-CNN** was significantly slower, averaging between **15s and 18s** per image (approx. 70-80x slower than YOLO), but offered deeper analysis of the scene.

### 2. Crowd Detection & Sensitivity
Faster R-CNN excelled in scenes with high occlusion and small objects:
* **Belmont Park:** Faster R-CNN detected **53 objects**, effectively spotting people in the crowd. YOLO only detected **4**.
* **SR-163 Traffic:** Faster R-CNN identified **64 objects** (mostly vehicles), whereas YOLO detected **33**.

### 3. Edge Detection Analysis
* The **Flower Fields** image registered the highest **Edge Density (0.2347)**.
* This metric successfully identified the image as the most texturally complex ("busy"), even though the deep learning models detected very few distinct objects (0 for YOLO, 7 for Faster R-CNN) due to the lack of distinct, trained object classes in the field of flowers.

## How to Run
1. Clone this repository.
2. Ensure you have **Jupyter Notebook** or **JupyterLab** installed.
3. Open the file:
   ```bash
   KRabanal_TakeHome_Code.ipynb
