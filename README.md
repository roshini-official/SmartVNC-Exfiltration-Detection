# SmartVNC – Security Against Data Exfiltration

![Project](https://img.shields.io/badge/Project-Cybersecurity-blue?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.11%2B-blue?style=flat-square&logo=python)
![Flask](https://img.shields.io/badge/Flask-Backend-black?style=flat-square&logo=flask)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red?style=flat-square&logo=streamlit)
![XGBoost](https://img.shields.io/badge/Machine_Learning-XGBoost-orange?style=flat-square)
![SQLite](https://img.shields.io/badge/Database-SQLite-blue?style=flat-square)

**An Intelligent Security Monitoring System for Detecting and Preventing Potential Data Exfiltration Through VNC Connections.**

---

## Project Overview

SmartVNC is a machine-learning-based security monitoring system designed to identify suspicious network activities and potential data exfiltration attempts associated with Virtual Network Computing (VNC) connections.

The system combines real-time network traffic monitoring, machine learning-based threat prediction, host-level security analysis, risk assessment, and alert generation to provide better visibility into potentially malicious activities.

By integrating network monitoring with intelligent detection mechanisms, SmartVNC aims to improve the identification of abnormal VNC communication patterns and support timely security responses.

## Objectives

- Monitor VNC network communication and traffic activities.
- Identify suspicious network behaviour using machine learning.
- Predict potential malicious activities through an XGBoost classification model.
- Analyse user and host activities using security rules.
- Generate risk-based alerts for suspicious events.
- Provide a centralized dashboard for security monitoring.
- Support prevention actions against detected threats.

## Key Features

| Feature | Description |
|---|---|
| Network Monitoring | Monitors VNC-related network traffic. |
| ML-Based Detection | Uses an XGBoost model to classify network activities. |
| Risk Assessment | Evaluates suspicious activities and risk levels. |
| Alert Generation | Generates alerts based on detected security events. |
| Interactive Dashboard | Displays monitoring information and security alerts. |
| Prevention Module | Supports configured prevention actions. |
| Database Management | Stores monitoring and alert information using SQLite. |

## System Architecture

SmartVNC follows a modular architecture that integrates network monitoring, machine learning, security analysis, and visualization.

```text
             VNC Client / VNC Server
                       |
                       v
                VNC Monitoring
                 (Scapy / RFB)
                       |
                       v
                  Live Data
                       |
                       v
                 Risk API
                   (Flask)
                       |
             +---------+---------+
             |                   |
             v                   v
        ML Prediction       Security Rules
         (XGBoost)          (CERT Dataset)
             |                   |
             +---------+---------+
                       |
                       v
                Risk Alert Engine
                       |
             +---------+---------+
             |                   |
             v                   v
          Dashboard          SQLite Database
          (Streamlit)               |
             |                      |
             +----------+-----------+
                        |
                        v
                 Prevention Module
```

## Technology Stack

### Programming Language
- Python

### Machine Learning
- XGBoost
- Scikit-learn
- Pandas
- NumPy
- Joblib

### Backend and API
- Flask
- REST API

### Frontend and Visualization
- Streamlit

### Network Monitoring
- Scapy
- TCP/IP
- VNC Remote Frame Buffer (RFB) Protocol

### Database
- SQLite

### Development Tools
- Visual Studio Code
- Git
- GitHub
- Jupyter Notebook

## Project Modules

### 1. Network Monitoring Module

Captures and monitors VNC-related network traffic and extracts relevant communication features.

### 2. Live Data Processing Module

Processes network activity and maintains the information required for real-time risk analysis.

### 3. Machine Learning Detection Module

Uses a trained XGBoost classification model to analyse network traffic features and identify suspicious behaviour.

### 4. Host-Level Security Analysis

Uses security rules derived from the CERT Insider Threat Dataset to identify potentially suspicious user and host activities.

### 5. Risk Alert Engine

Evaluates detection results and generates alerts based on the configured risk assessment logic.

### 6. Dashboard Module

Provides an interactive Streamlit interface to visualize monitoring information, detected activities, risk levels, and security alerts.

### 7. Prevention Module

Implements configured security response actions to help prevent suspicious activities.

## Project Structure

```text
SmartVNC/
│
├── dashboard/
│   └── Dashboard components
│
├── database/
│   └── Database components
│
├── datasets/
│   └── Training and testing datasets
│
├── demo_files/
│   └── Demonstration files
│
├── live_data/
│   └── Live monitoring data components
│
├── ml-engine/
│   └── Machine learning models and processing
│
├── monitoring/
│   └── Network monitoring components
│
├── tests/
│   └── Testing scripts
│
├── config.py
├── requirements.txt
├── run_smartvnc.bat
├── run_smartvnc.ps1
└── README.md
```

## Datasets Used

SmartVNC uses two security datasets for different detection purposes.

### 1. CICIDS2017 Dataset

Used for network traffic analysis and machine learning-based classification of suspicious network activities.

### 2. CERT Insider Threat Dataset (r4.2)

Used for analysing employee and host-related activity patterns through rule-based security analysis.

The two datasets support separate detection components and are not joined through row-level matching.

## Installation and Setup

### Prerequisites

- Windows 10 / Windows 11
- Python 3.11 or 3.12
- Visual Studio Code
- Git
- Required network monitoring permissions
- Npcap, if required by the Scapy monitoring configuration

### Step 1: Clone the Repository

```bash
git clone https://github.com/roshini-official/SmartVNC-Exfiltration-Detection.git
```

### Step 2: Navigate to the Project

```bash
cd SmartVNC-Exfiltration-Detection
```

### Step 3: Create a Virtual Environment

```bash
py -3.11 -m venv .venv
```

### Step 4: Activate the Environment

```powershell
.\.venv\Scripts\Activate.ps1
```

### Step 5: Install Dependencies

```bash
python -m pip install --upgrade pip
```

```bash
python -m pip install -r requirements.txt
```

## Running the Application

SmartVNC consists of multiple components that work together.

The repository includes Windows launcher scripts.

Using PowerShell:

```powershell
.\run_smartvnc.ps1
```

Alternatively, using Command Prompt:

```cmd
run_smartvnc.bat
```

Follow the launcher's output to verify that the required services start successfully.

### Application Endpoints

| Component | Address |
|---|---|
| Risk Prediction API | http://127.0.0.1:5000 |
| Streamlit Dashboard | http://localhost:8501 |
| VNC Communication | TCP Port 5900 |

**Note:** The API and dashboard addresses are local application endpoints. The VNC port is used for VNC communication, not for opening the dashboard.

## Dashboard

The SmartVNC dashboard provides a centralized view of security monitoring information.

It is designed to display:

- Network monitoring information.
- Suspicious activity detection.
- Machine learning prediction results.
- Risk levels and security alerts.
- Historical monitoring records.

### Dashboard Screenshots

Add your actual project screenshots here after running the application.

```markdown
![SmartVNC Dashboard](screenshots/dashboard.png)
```

## Security and Prevention

SmartVNC combines machine learning predictions and rule-based security analysis to support the detection of potentially suspicious activities.

The prevention component provides configured response mechanisms based on the detection results.

All monitoring and prevention operations should be tested in an authorized environment.

## Future Enhancements

- Improve machine learning detection accuracy.
- Extend real-time network monitoring capabilities.
- Introduce advanced anomaly detection techniques.
- Improve automated incident response.
- Enhance dashboard analytics and reporting.
- Support additional network protocols and security monitoring scenarios.

## Project Team

**Final Year Major Project – Batch 4**

| S. No. | Team Member |
|---|---|
| 1 | Pranathi D K |
| 2 | Niveditha Y |
| 3 | Rakshitha L |
| 4 | Roshini Sri S |

**Project Guide:** Dr. Mahesh A.

## Project Information

- **Project Title:** SmartVNC – Security Against Data Exfiltration
- **Domain:** Cybersecurity and Machine Learning
- **Project Type:** Final Year Major Project
- **Institution:** Sri Sairam College of Engineering

## License

This project is developed for academic and educational purposes. Refer to the original repository's license and dataset licensing terms before redistribution.

---

**SmartVNC – Intelligent Monitoring. Proactive Detection. Enhanced Security.**

Developed as a Final Year Engineering Project.
