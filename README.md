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
* `Asian Market.jpg`: The source test image.
* `image_detect_result.jpg`: Output showing successful object bounding boxes.
* `video_tracking_result.avi`: Output showing active object tracking with IDs.
* `webcam_test_demo.avi`: Final evidence of the real-time webcam test.
* `screenshots/`: containing Command Prompt (CMD) logs of script execution.



How to Run the System
If you don't have the libraries or tech stack installed, follow these steps to set up a "Virtual Environment" (a clean sandbox) on your computer.

1. Clone & Setup
Bash
# Clone the repository
git clone [YOUR_GITHUB_LINK_HERE]
cd [YOUR_REPO_FOLDER_NAME]

# Create a virtual environment
python -m venv venv

# Activate the environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
2. Install Dependencies
This command installs PyTorch, OpenCV, and YOLOv8 automatically:

Bash
pip install -r requirements.txt
3. Execute
Webcam Test: python lab_1.py --source 0
Video Tracking: python lab_1.py --source video_tracking_result.avi


###  Learnings & Observations
* **Confidence Behavior:** Setting the confidence to **0.35** ensures that only high-probability detections are rendered, reducing false positives in the video feed.
* **Tracking vs. Detection:** Detection identifies objects in isolated frames, while Tracking maintains the identity of those objects throughout the duration of the video.
* **Model Limitations:** Observed factors like lighting and object occlusion (objects blocking each other) can impact the model's ability to maintain a consistent Tracking ID.


 ### Lab 1: Object Detection and Tracking Results Analysis
 ### 1. Static Image Detection
In the provided urban street and market scenes, the model successfully identified a high density of objects.

Class Frequency: The "person" class was the most frequently detected, particularly in the market scene where over 10 individuals were identified.

Confidence Threshold: Using a threshold of 0.35, the model captured major objects like a bus (0.36) and cars (0.39 - 0.54).

Observation: Lowering the confidence to 0.10 would likely reveal smaller or occluded unique objects such as handbags or umbrellas that are currently filtered out.

 ### 2. Video Tracking Performance
The tracking script was applied to a highway surveillance video using the ByteTrack algorithm.

Persistent IDs: The model assigned unique, persistent IDs to vehicles (e.g., id:78), maintaining their identity across multiple frames.

Scalability: By the end of the video, the tracker successfully cataloged more than 10 unique objects, with IDs reaching as high as 182.

Class Diversity: Beyond cars, the model correctly distinguished a train with a confidence of 0.37.

 ### 3. Real-Time Webcam Test
Detection Accuracy: The model maintained a high confidence score of 0.92 for the "person" class during the live feed.

Robustness: Even with rapid movement or partial occlusion, the tracking ID (id:1) remained stable.

