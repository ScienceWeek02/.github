# EEG Seizure Detection System

A real-time epileptic seizure detection system using EEG signals. The application processes EEG data via MQTT, uses a machine learning model for prediction, and displays results through an interactive web interface.
![image](https://github.com/user-attachments/assets/dcd5aa09-5aee-4fed-9bd9-f65792606afd)



## System Overview

This system consists of three main components:
1. **Node-RED Flow**: Processes incoming EEG data from MQTT
2. **Python Flask Backend**: Hosts the web application and ML model
3. **Web Interface**: Real-time visualization dashboard

## Prerequisites

- Python 3.8+ 
- Node.js and npm
- Node-RED
- MQTT broker (Mosquitto recommended)

## Installation Guide

### 1. MQTT Broker Setup

First, install and start the Mosquitto MQTT broker:

```bash
# Ubuntu/Debian
sudo apt-get install mosquitto mosquitto-clients
sudo systemctl start mosquitto
sudo systemctl enable mosquitto  # Start on boot

# For macOS with Homebrew
brew install mosquitto
brew services start mosquitto
```

### 2. Node-RED Setup

Install Node-RED globally:

```bash
npm install -g node-red
```

Start Node-RED:

```bash
node-red
```

Access the Node-RED editor at `http://localhost:1880`.

#### Import the Flow into Node-RED:

1. In the Node-RED interface, click on the menu (≡), then "Import"
2. Click "select a file to import"
3. Choose the `flows.json` file from this repository
4. Click "Import"
5. Deploy the flow by clicking the "Deploy" button

### 3. Python Application Setup

#### Create and activate a virtual environment:

```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On Windows
venv\Scripts\activate
# On Unix or MacOS
source venv/bin/activate
```

#### Install all required dependencies:

```bash
pip install flask flask-socketio paho-mqtt numpy pandas scikit-learn tensorflow
```

#### Start the application:

```bash
python3 webapp/app.py
```

Access the web application at `http://localhost:5000`.

## Using the Application

1. **Start the Simulator**: Click "Start the EEG Simulation" on the web interface to begin generating test data
2. **Adjust Parameters**: 
   - Use the interval dropdown to set the speed of data generation
   - Adjust the threshold slider to change the seizure detection sensitivity
3. **View Results**: Monitor real-time EEG signals, detection status, and history
4. **Stop Simulation**: Click "Stop Simulation" when finished

