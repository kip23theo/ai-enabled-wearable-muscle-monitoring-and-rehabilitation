# AI-Enabled Wearable System for Muscle Monitoring, Injury Risk Classification & Rehabilitation

**An integrated wearable technology platform combining Electromyography (EMG), accelerometer sensors, embedded systems, and Artificial Intelligence for muscle activity monitoring, preliminary injury risk classification, and rehabilitation progress assessment.**

<p align="center">
  <strong>Biomedical Engineering | Wearable Technology | IoT | Machine Learning | Rehabilitation</strong>
</p>

---

## 1. Project Overview

Muscle injuries, fatigue, and improper movement patterns can affect exercise performance and rehabilitation outcomes. Monitoring muscle activity alongside joint movement can provide useful information about exercise execution and recovery progress.

This project presents an **AI-enabled wearable monitoring system** designed to analyze biceps muscle activity and arm movement during arm-curl exercises.

The system integrates surface Electromyography (EMG) and ADXL345 accelerometer sensors with ESP32 microcontrollers to capture physiological and movement-related data. The collected readings are processed through a Python-based application that provides real-time muscle activity visualization, joint movement analysis, and rehabilitation session tracking.

An additional machine learning module uses a Random Forest classifier to provide preliminary muscle injury risk classification based on user profile parameters and EMG readings.

The platform combines wearable sensing, interactive 3D anatomical visualization, and data-driven analysis into a unified monitoring environment.

## 2. Key Capabilities

| Feature | Description |
|---|---|
| Wearable Muscle Monitoring | Captures biceps muscle electrical activity using surface EMG |
| Accelerometer-Based Motion Tracking | Monitors forearm and upper-arm orientation |
| Real-Time 3D Visualization | Displays an interactive anatomical arm model |
| Dynamic Muscle Visualization | Represents changing EMG intensity through visual muscle feedback |
| Joint Angle Estimation | Estimates elbow movement using accelerometer readings |
| Range of Motion Assessment | Tracks elbow ROM during exercise sessions |
| Automatic Repetition Counting | Detects completed arm-curl repetitions |
| Preliminary Risk Classification | Applies Random Forest machine learning for Low, Moderate, and High risk categories |
| Rehabilitation Progress Tracking | Stores session history, ROM, repetitions, EMG readings, and pain records |
| Interactive Dashboard | Presents exercise history and recovery-related progress graphs |

## 3. System Architecture

The proposed system consists of three interconnected layers.

### A. Wearable Sensor Layer

The wearable hardware captures muscle activity and arm movement through:

- **Muscle Sensor V3:** Acquires surface EMG signals from the biceps.
- **ADXL345 Accelerometers:** Capture movement and orientation data from the forearm and upper arm.
- **EMG Electrodes:** Establish the interface between the muscle and EMG sensor.

### B. Embedded Processing Layer

Two ESP32 microcontrollers interface with the sensor modules and facilitate data acquisition.

The accelerometer readings and EMG values are transmitted to the application through serial communication for further processing.

### C. Application and Intelligence Layer

A Flask-based web application handles:

- Sensor data acquisition and processing.
- Elbow angle and ROM estimation.
- Repetition detection.
- EMG signal smoothing and visualization.
- Machine learning-based risk classification.
- Exercise session storage and progress analysis.

The application also provides an interactive 3D arm model for visualizing movement and muscle activity.

## 4. Hardware Components

| Hardware | Quantity | Function |
|---|---:|---|
| ESP32 Microcontroller | 2 | Embedded processing and sensor communication |
| ADXL345 Accelerometer | 2 | Forearm and upper-arm movement tracking |
| Muscle Sensor V3 | 1 | Surface EMG signal acquisition |
| EMG Electrodes | As required | Muscle electrical signal detection |
| 16×2 LCD | 1 | Hardware display |
| Battery / Power Supply | As required | System power supply |

## 5. Technology Stack

**Embedded Systems**
- ESP32
- ADXL345
- Arduino IDE
- C/C++

**Backend and Data Processing**
- Python
- Flask
- NumPy
- Pandas
- PySerial
- SQLite

**Frontend and Visualization**
- HTML5
- CSS3
- JavaScript
- Three.js
- Chart.js

**Artificial Intelligence and Machine Learning**
- Scikit-learn
- Random Forest Classifier
- Joblib

## 6. Machine Learning-Based Preliminary Risk Classification

The system incorporates a machine learning module to classify potential muscle injury risk using selected physiological and user-profile parameters.

### Model Inputs

| Input Parameter | Data Source |
|---|---|
| Age | User profile |
| Gender | User profile |
| Muscle Density | User profile |
| EMG Readings | Muscle Sensor V3 or manual input |

### Classification Output

The Random Forest classifier generates one of three preliminary risk categories:

- **Low Risk**
- **Moderate Risk**
- **High Risk**

The application supports two prediction modes:

1. **Sensor-Based Prediction:** Uses the user's profile information and current EMG readings acquired from the wearable sensor.
2. **Manual Prediction:** Allows users to enter the required parameters and obtain a classification without an active sensor connection.

The predicted category and associated class scores are displayed through the risk prediction interface.

## 7. Rehabilitation and Exercise Monitoring

A major component of the platform is its ability to monitor exercise sessions and maintain a record of rehabilitation-related progress.

### Real-Time Exercise Monitoring

The exercise interface provides:

- Interactive 3D anatomical arm visualization.
- Right and left arm viewing options.
- Dynamic biceps muscle visualization based on EMG intensity.
- Live elbow angle estimation.
- Forearm and upper-arm movement monitoring.
- Repetition counting.
- Exercise duration tracking.

### Rehabilitation Progress Assessment

Exercise session information is stored for subsequent review and comparison.

The dashboard records:

- Elbow range of motion.
- Minimum and maximum joint angles.
- Exercise repetitions.
- EMG average and peak values.
- Session duration.
- Recorded pain levels and notes.

These measurements provide a basis for observing changes in exercise performance and movement range across sessions.

## 8. Web Application Modules

### Home Page
Introduces the wearable muscle monitoring platform and provides navigation to the main application features.

### Exercise Monitoring Interface
Provides real-time sensor feedback, interactive 3D anatomical visualization, muscle activity representation, joint angle estimation, and repetition counting.

### Risk Prediction Interface
Performs preliminary muscle injury risk classification using EMG readings and user profile information.

### User Dashboard
Displays exercise history, ROM measurements, repetitions, EMG trends, and rehabilitation-related session records.

### User Profile
Allows users to manage their age, gender, muscle density, and target range of motion.

### Session Reports
Provides detailed information about individual exercise sessions and recorded measurements.

## 9. Application Preview

The platform includes an interactive web interface designed to combine physiological monitoring, movement analysis, and machine learning outputs.

**Exercise Monitoring – Interactive 3D Arm**

Add your screenshot here:

`assets/exercise-monitoring.png`

**Muscle Injury Risk Prediction – Web Interface**

Add your screenshot here:

`assets/risk-prediction.png`

## 10. Project Directory Structure

```text
ai-enabled-wearable-muscle-monitoring-and-rehabilitation/
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
│   ├── base.html
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   ├── profile.html
│   ├── dashboard.html
│   ├── exercise.html
│   ├── risk.html
│   └── report.html
│
├── static/
│   ├── style.css
│   └── js/
│       ├── arm3d.js
│       └── charts.js
│
└── assets/
    ├── exercise-monitoring.png
    └── risk-prediction.png
```

*Note: The assets directory is for screenshots you add to the repository.*

## 11. Installation and Execution

### Prerequisites

- Python installed on your system.
- ESP32 development environment (for hardware integration).
- Connected wearable sensors for real-time monitoring.
- USB serial connection for sensor communication.

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/ai-enabled-wearable-muscle-monitoring-and-rehabilitation.git

cd ai-enabled-wearable-muscle-monitoring-and-rehabilitation
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Configure Machine Learning Models

Place the trained model files in the `models/` directory:

```text
models/
├── best_emg_muscle_risk_model.pkl
└── model_metadata.pkl
```

**Important:** These trained model files are not included in the current source-code package. They must be supplied separately for machine learning-based risk prediction. Use a compatible Scikit-learn version matching the model training environment.

### Step 4: Connect the Hardware

Connect the ESP32-based sensor system and configure the appropriate serial port.

The application expects sensor readings in the following format:

```text
Forearm_X, Forearm_Y, Forearm_Z,
UpperArm_X, UpperArm_Y, UpperArm_Z, EMG
```

The application uses a default serial port of COM4 at 9600 baud. The serial port can be changed through the application arguments.

### Step 5: Run the Application

**For real-time hardware integration:**

```bash
python app.py
```

**For simulation without physical sensors:**

```bash
python app.py --simulate
```

**For an alternative serial port:**

```bash
python app.py --port COM5
```

### Step 6: Access the Web Application

Open your browser and navigate to:

```text
http://127.0.0.1:5000
```

## 12. Research Significance

This project explores the integration of wearable biomedical sensing and artificial intelligence for exercise monitoring and rehabilitation-related applications.

Its primary contributions include:

- Integration of surface EMG and accelerometer-based sensing for combined muscle activity and movement monitoring.
- Real-time visualization of arm movement through an interactive 3D anatomical model.
- Estimation of joint movement, range of motion, and exercise repetitions.
- Preliminary machine learning-based muscle injury risk classification.
- Session-based rehabilitation progress monitoring through stored physiological and movement measurements.

## 13. Future Scope

Potential extensions of this work include:

- Integration of additional physiological sensors for comprehensive muscle monitoring.
- Advanced muscle fatigue and activity pattern analysis.
- Training and validation using larger, clinically relevant datasets.
- Personalized rehabilitation progress assessment.
- Mobile application development for remote monitoring.
- Cloud-based storage and longitudinal rehabilitation analytics.
- Extension to additional joints and rehabilitation exercises.

## 14. Limitations and Disclaimer

This implementation is an academic research prototype intended for experimental muscle activity monitoring, exercise analysis, and preliminary risk classification.

The machine learning model used in the current implementation was trained using synthetic data. Consequently, its classification results should not be interpreted as clinically validated predictions or evidence of actual injury probability.

The system is not intended to diagnose injuries, replace medical assessments, or independently prescribe rehabilitation treatments. Clinical evaluation and validation using real-world patient data would be necessary before any medical application.

## 15. Author

**Crispin Theophane**

B.Tech – Electronics and Computer Engineering (AI & ML)  
CHRIST (Deemed to be University), Bengaluru

---

**Research Project | Wearable Biomedical Systems | Artificial Intelligence | Rehabilitation Technology**

