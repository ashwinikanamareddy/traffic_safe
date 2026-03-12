🚦 AI-Powered Traffic Queue Analysis & Violation Detection System
📌 Overview

Urban intersections in India face severe congestion, unsafe driving behavior, and frequent traffic rule violations. Traditional traffic monitoring systems rely on fixed-time signals and manual supervision, which lack real-time adaptability.

This project presents an AI-powered traffic intelligence system that uses computer vision and multi-object tracking to analyze traffic footage and generate actionable insights such as:

🚗 Vehicle Detection & Tracking

📏 Lane-wise Queue Length & Density Estimation

🚦 Red-Light Violation Detection

⚠️ Rash Driving Detection

📊 Real-Time Analytics Dashboard

The system processes pre-recorded traffic video footage and presents insights through a Streamlit-based web dashboard.

🎯 Problem Statement

Design and implement a vision-based traffic analysis system that:

Detects and tracks multiple vehicle types

Estimates queue length and traffic density per lane

Identifies red-light jumping and rash driving

Displays results via a web dashboard

Generates annotated video outputs

🏗️ System Architecture
Input Video
     ↓
Vehicle Detection (YOLO)
     ↓
Multi-Object Tracking
     ↓
Lane Assignment
     ↓
Queue Analysis
     ↓
Violation Detection
     ↓
Dashboard Visualization
     ↓
Annotated Video Export
🔍 Core Features
1️⃣ Vehicle Detection

Deep learning-based detection model

Detects:

Cars

Bikes

Buses

Trucks

Autos

Each detected object is assigned a bounding box and class label.

2️⃣ Multi-Object Tracking

Assigns unique ID to each vehicle

Maintains ID consistency across frames

Tracks vehicle trajectory history

Handles moderate occlusions

Output Example:

ID 12 | Car
ID 5  | Bus
ID 18 | Bike
3️⃣ Manual Lane Configuration

User manually defines lanes by clicking exactly 4 points

Each lane is a quadrilateral

Lane polygons saved in JSON format

Enables accurate lane-wise analytics

4️⃣ Stop Line Configuration

User draws stop line using 2 clicks

Used for red-light violation detection

Saved as JSON configuration

5️⃣ Queue Length Estimation

Queue Length per lane:

Queue Length = Number of vehicles before stop line
6️⃣ Queue Density Estimation
Density = Vehicle Count / Lane Area

Density Classification:

Low: 0 – 5 vehicles

Medium: 6 – 10 vehicles

High: >10 vehicles

7️⃣ Red-Light Violation Detection

A violation is detected when:

Signal == RED
AND
Vehicle crosses stop line

System:

Highlights violating vehicle in red

Logs vehicle ID

Records timestamp

Prevents duplicate counting

8️⃣ Rash Driving Detection

Based on trajectory heuristics:

Sudden acceleration

Erratic movement

Abnormal speed threshold

📊 Dashboard Features

The Streamlit dashboard displays:

🔹 Live Annotated Video

Bounding boxes

Vehicle IDs

Lane boundaries

Stop line

Violations highlighted

🔹 Real-Time Metrics

Total Vehicle Count

Total Violations

Average Density

Current Frame Number

🔹 Lane-Wise Analytics

| Lane ID | Vehicle Count | Density | Status |

🔹 Vehicle Class Distribution

Bar chart of detected vehicle types

🔹 Violation Monitor

| Vehicle ID | Lane | Timestamp | Violation Type |

🔹 Export Option

Download annotated video

Export violation report

🛠️ Tech Stack

Python

OpenCV

YOLO (Detection Model)

Multi-Object Tracker (ByteTrack/DeepSORT)

Streamlit (Web Interface)

NumPy

JSON (Configuration Storage)

📂 Project Structure
Traffic-Intelligence-System/
│
├── app.py
├── lane_config.py
├── stopline_config.py
├── tracker_module.py
├── analyzer.py
├── models/
├── config/
│   ├── lanes.json
│   └── stopline.json
├── output/
├── requirements.txt
└── README.md
▶️ How to Run the Project
1️⃣ Clone Repository
git clone https://github.com/your-username/traffic-intelligence-system.git
cd traffic-intelligence-system
2️⃣ Install Dependencies
pip install -r requirements.txt
3️⃣ Run Application
streamlit run app.py
4️⃣ Open in Browser
http://localhost:8501
⚠️ Assumptions & Limitations

Uses pre-recorded traffic video only

Manual lane configuration required

Extreme occlusion may reduce tracking accuracy

Heavy rain / poor lighting may reduce detection accuracy

Signal state controlled manually

🎓 Evaluation Highlights

✔ Accurate vehicle detection
✔ Stable multi-object tracking
✔ Lane-wise queue analytics
✔ Red-light violation detection
✔ Explainable modular architecture
✔ Clean dashboard visualization

📈 Future Improvements

Automatic lane detection

Signal state auto-detection

Speed estimation using homography

Real-time CCTV feed integration

AI-based congestion prediction

👩‍💻 Author

Ashwini Kanamareddy
B.Tech CSE
Traffic Intelligence System – Hackathon Project

🏆 Conclusion

This system demonstrates how computer vision can transform traditional traffic monitoring into an intelligent, data-driven analytics platform capable of:

Seeing traffic

Tracking vehicles

Understanding congestion

Detecting violations

Supporting smarter traffic management
