# Muscle Injury Risk Prediction Using EMG and Accelerometer Sensors

An intelligent wearable-based system that monitors muscle activity and arm movement during exercise using **Electromyography (EMG), accelerometer sensors, and Machine Learning**. The system provides real-time muscle strength visualization, range-of-motion tracking, exercise repetition counting, and muscle injury risk prediction through an interactive web application.

## Overview

Muscle injuries can occur during resistance training due to excessive muscle loading, fatigue, or improper exercise movements. This project introduces a wearable monitoring system designed to analyze biceps muscle activity and arm movement during arm-curl exercises.

The system integrates surface EMG and accelerometer sensors with ESP32 microcontrollers to collect physiological and movement data. A Flask-based web application processes the readings, visualizes arm movements through an interactive 3D model, and uses a machine learning model to classify potential muscle injury risk.

## Key Features

- **Real-Time Muscle Monitoring:** Captures biceps muscle activity using a surface EMG sensor.
- **Motion Tracking:** Uses ADXL345 accelerometers to monitor forearm and upper-arm movement.
- **Interactive 3D Arm Visualization:** Displays a 3D anatomical arm model with muscles, bones, and tendons.
- **Muscle Strength Visualization:** Dynamically changes the biceps muscle appearance based on EMG intensity.
- **Range of Motion (ROM):** Estimates elbow movement and tracks joint angles during exercise.
- **Repetition Counting:** Automatically counts arm-curl repetitions.
- **Machine Learning-Based Risk Prediction:** Uses a Random Forest classifier to categorize muscle injury risk into Low, Moderate, and High categories.
- **Live and Manual Prediction:** Supports sensor-based predictions and manually entered user information.
- **Exercise Dashboard:** Stores exercise sessions and displays progress through graphical reports.
- **Session Tracking:** Records repetitions, ROM, EMG readings, and exercise progress.

## System Architecture

The system consists of three main components:

1. **Sensor Layer:** Two ADXL345 accelerometers capture arm movement, while a Muscle Sensor V3 captures biceps EMG activity.
2. **Processing Layer:** Two ESP32 microcontrollers collect sensor readings and transmit data to the computer through serial communication.
3. **Application Layer:** A Python Flask application processes sensor data, performs movement analysis, displays the 3D arm model, stores exercise sessions, and generates machine learning-based risk predictions.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 (2 units) | Sensor data acquisition and communication |
| ADXL345 (2 units) | Accelerometer-based movement tracking |
| Muscle Sensor V3 | Surface EMG signal acquisition |
| EMG Electrodes | Detect muscle electrical activity |
| 16×2 LCD | Hardware-level display |
| Battery / Power Supply | Powers the wearable system |

## Software and Technologies

- **Programming:** Python, C/C++
- **Backend:** Flask
- **Frontend:** HTML, CSS, JavaScript
- **3D Visualization:** Three.js
- **Data Visualization:** Chart.js
- **Machine Learning:** Scikit-learn, Random Forest
- **Data Processing:** NumPy, Pandas
- **Communication:** Serial Communication (PySerial)
- **Database:** SQLite
- **Embedded Platform:** ESP32

## Machine Learning-Based Risk Prediction

The machine learning module analyzes the following input parameters:

- Age
- Muscle Density
- Gender
- EMG Readings

The Random Forest classifier processes these features and predicts one of three risk categories:

- Low Risk
- Moderate Risk
- High Risk

The system supports both real-time EMG readings from the connected sensor and manually entered values.

## Application Modules

**1. Exercise Monitoring**

An interactive 3D arm model displays muscle activity and movement during arm curls. Users can monitor elbow angles, range of motion, repetitions, and EMG strength.

**2. Risk Prediction**

Uses user profile information and EMG readings to generate muscle injury risk classifications.

**3. User Dashboard**

Maintains exercise history and visualizes session-wise progress, including ROM, repetitions, EMG strength, and recorded pain levels.

**4. User Profile**

Allows users to manage personal information, muscle density, gender, age, and target range of motion.

## Project Structure

```text
muscle-injury-risk-prediction/
│
├── app.py
├── requirements.txt
├── README.md
│
├── models/
│   ├── best_emg_muscle_risk_model.pkl
│   └── model_metadata.pkl
│
├── templates/
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   ├── profile.html
│   ├── dashboard.html
│   ├── exercise.html
│   ├── risk.html
│   └── report.html
│
└── static/
    ├── style.css
    └── js/
        ├── arm3d.js
        └── charts.js
```

## Installation and Setup

**1. Clone the repository**

```bash
git clone https://github.com/YOUR-USERNAME/muscle-injury-risk-prediction.git

cd muscle-injury-risk-prediction
```

**2. Install dependencies**

```bash
pip install -r requirements.txt
```

**3. Add trained machine learning models**

Place the required trained model files inside the `models/` directory:

```text
models/
├── best_emg_muscle_risk_model.pkl
└── model_metadata.pkl
```

These model files are required for risk prediction and are not included in the current project ZIP.

**4. Run the application**

For real sensor connections:

```bash
python app.py
```

For testing without physical hardware:

```bash
python app.py --simulate
```

**5. Open the application**

Navigate to:

```text
http://127.0.0.1:5000
```

## Future Enhancements

- Integration of additional wearable physiological sensors.
- Improved muscle fatigue analysis.
- Enhanced injury risk prediction using larger real-world datasets.
- Mobile application integration for remote monitoring.
- Personalized rehabilitation and exercise recommendations.
- Cloud-based storage and remote patient monitoring.

## Disclaimer

This project is developed as an academic and research prototype for exercise monitoring and machine learning-based risk classification. Its predictions are not clinically validated and should not be considered a medical diagnosis or a substitute for professional medical assessment.

## Author

**Crispin Theophane**

B.Tech – Electronics and Computer Engineering (AI & ML)

CHRIST (Deemed to be University), Bengaluru

---

*Developed as a wearable technology and machine learning project integrating embedded systems, biomedical sensing, and interactive 3D visualization.*
