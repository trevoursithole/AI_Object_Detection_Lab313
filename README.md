# CMPG 313: Artificial Intelligence - Lab 1
## Training a Machine Learning Model with YOLOv8

###  Project Objective
This project demonstrates the application of Computer Vision using the **YOLOv8** framework. The goal is to implement a machine learning model capable of identifying and tracking objects in static images, pre-recorded video, and live webcam feeds. A key focus is the analysis of data collection and the functional differences between detection and tracking.

###  Technical Setup
- **Framework:** YOLOv8 (Ultralytics)
- **Language:** Python 3.x
- **Libraries:** `opencv-python`, `ultralytics`
- **Tracking Algorithm:** ByteTrack

### Implementation Details
The project utilizes the `lab_1.py` script to perform three distinct tests:

1. **Image Test (Detection):** Uses `model.predict` with a confidence threshold of **0.35**. 
2. **Video Test (Tracking):** Processes "Cars Moving On Road Footage.mp4" using `model.track` to assign unique temporal IDs to vehicles.
3. **Webcam Test:** Real-time application where the user is recognizable in the data to verify model responsiveness and personal interaction.



### Repository Structure
Based on the assessment requirements, this repository contains:
* `lab_1.py`: The core Python implementation.
* `Cars Moving On Road Footage.mp4`: The source test video.
* `result_image.jpg`: Output showing successful object bounding boxes.
* `result_video.avi`: Output showing active object tracking with IDs.
* `webcam_demo.mp4`: Final evidence of the real-time webcam test.
* `screenshots/`: containing Command Prompt (CMD) logs of script execution.

###  Learnings & Observations
* **Confidence Behavior:** Setting the confidence to **0.35** ensures that only high-probability detections are rendered, reducing false positives in the video feed.
* **Tracking vs. Detection:** Detection identifies objects in isolated frames, while Tracking maintains the identity of those objects throughout the duration of the video.
* **Model Limitations:** Observed factors like lighting and object occlusion (objects blocking each other) can impact the model's ability to maintain a consistent Tracking ID.

---
*Submitted by Trevour Sithole for CMPG 313 Practical Assessment.*
