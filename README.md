# Automatic-Car-number-Plate-Detection


Data
The video used in the tutorial can be downloaded here.....https://www.pexels.com/video/traffic-flow-in-the-highway-2103099/



Number Plate Detection and Tracking

This project implements a pipeline for detecting and tracking vehicles and their license plates in a video, recognizing license plate text, interpolating missing frames, and generating an annotated output video with bounding boxes and license plate information.

Overview

The pipeline consists of several scripts:





Vehicle and License Plate Detection: Uses YOLOv8 models to detect vehicles and license plates in a video.



Tracking: Tracks vehicles across frames using the SORT algorithm.



License Plate Reading: Extracts license plate text using EasyOCR.



Interpolation: Interpolates missing frames to ensure smooth tracking.



Visualization: Annotates the video with vehicle and license plate bounding boxes, license plate text, and cropped license plate images.

The project outputs:





A CSV file (test.csv) with detection and tracking results.



An interpolated CSV file (test_interpolated.csv) with filled-in missing frames.



An annotated output video (out.mp4) showing tracked vehicles and license plates.

Prerequisites





Operating System: Windows (tested on Windows with paths like D:\number plate detection).



Python: Version 3.8 or higher.



Dependencies: Listed in requirements.txt.



Input Video: An MP4 video file (e.g., sample.mp4) in the project directory.



YOLO Models:





yolov8n.pt: Pre-trained YOLOv8 model for vehicle detection (download from Ultralytics).



license_plate_detector.pt: Custom-trained YOLO model for license plate detection (not provided; you must supply your own).



FFmpeg (optional): For video conversion if the output video is unplayable.                                                                                                                              


 Project Setup
Make an environment with python=3.10 using the following command
conda create --prefix ./env python==3.10 -y
Activate the environment
source activate ./env
Install the project dependencies using the following command
pip install -r requirements.txt
Run main.py with the sample video file to generate the test.csv file
python main.py
Run the add_missing_data.py file for interpolation of values to match up for the missing frames and smooth output.
python add_missing_data.py
Finally run the visualize.py passing in the interpolated csv files and hence obtaining a smooth output for license plate detection.
python visualize.py

