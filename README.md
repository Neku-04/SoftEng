# 💧 Detecting Water Leak Using a Smart IoT-Based Anomaly Detection System

An intelligent IoT-based system that monitors real-time water flow and detects potential leaks using a Machine Learning model powered by Random Forest Classification. The system runs on a Raspberry Pi.

---

## 📌 Project Overview

Water leakage leads to water waste, increased utility costs, and structural damage. This project presents a Smart IoT-Based Water Leak Detection System that integrates:

- Real-time water flow sensing
- MQTT-based communication
- Edge computing with Raspberry Pi
- Machine Learning (Random Forest Classifier)
- Automatic water shut-off mechanism

The system classifies water flow behavior as **Normal** or **Leak Detected** and automatically activates a solenoid valve to stop water flow when necessary.

---

## 🎯 Objectives

- Design and develop an IoT-based smart water leak detection and isolation prototype using a Raspberry Pi microcontroller.

- Integrate a Random Forest Classifier as a supervised anomaly detection algorithm to classify water flow conditions into **normal**, **minor leak**, **moderate leak** and **major leak**, based on labeled training data.

- Evaluate the prototype's effectiveness in detecting and isolating water leaks by measuring its accuracy, responsiveness, and reliability under controlled scenarios, with LED-based alerts and automatic valve actuation.

---

## 🏗️ System Architecture

### 🔌 Hardware Layer

- Raspberry Pi
- Water Flow Sensor
- Solenoid Valve
- Relay Module (for valve control)
- Power Supply

### 🌐 Communication Layer

- MQTT Protocol
- HiveMQ (MQTT Broker)

### 🧠 Intelligence Layer

- Python Data Processing
- Random Forest Classifier
- Real-time Prediction Engine

### 🌍 Remote Access

- ngrok (Secure Tunnel for Remote Monitoring)

---

## 🔄 System Workflow

1. Water flow sensor measures real-time flow rate.
2. Raspberry Pi reads sensor data.
3. Data is published via MQTT to HiveMQ.
4. Python script preprocesses incoming data.
5. Trained Random Forest model predicts:
   - Normal Usage
   - Leak Detected
6. If a leak is detected:
   - Alert is triggered
   - Solenoid valve is activated via relay
   - Water supply is automatically shut off

---

## 🧠 Machine Learning Model

### Model Used

**Random Forest Classifier (RFC)**

### Why Random Forest?

- Handles non-linear relationships
- High classification accuracy
- Resistant to overfitting
- Suitable for structured sensor data

### Training Process

- Dataset collected from real water flow readings
- Data labeled as:
  - Normal Flow
  - Leak Condition
- Features may include:
  - Flow rate
  - Duration
  - Sudden spikes
  - Continuous abnormal flow
- Model trained using scikit-learn
- Model saved using joblib or pickle

---

## 🛠️ Technologies Used

### Hardware

- Raspberry Pi
- Water Flow Sensor
- Solenoid Valve
- Relay Module

### Software

- Python
- Arduino IDE (used for sensor configuration/programming if applicable)
- MQTT Protocol
- HiveMQ
- ngrok
- Scikit-learn
- Raspberry Pi Imager

---

## 🚀 Installation & Setup

### 1️⃣ Raspberry Pi Setup

1. Flash Raspberry Pi OS using Raspberry Pi Imager.
2. Install dependencies:

```bash
pip install paho-mqtt numpy pandas scikit-learn joblib RPi.GPIO

```

### 2️⃣ Hardware Setup

- Connect water flow sensor to Raspberry Pi GPIO
- Connect relay module to Raspberry Pi
- Connect solenoid valve to relay
- Ensure proper external power supply for solenoid valve

### 3️⃣ Model Training

```python
   from sklearn.ensemble import RandomForestClassifier
   import joblib
   
   model = RandomForestClassifier(n_estimators=100, random_state=42)
   model.fit(X_train, y_train)
   
   joblib.dump(model, "water_leak_model.pkl")

```

### 4️⃣ Real-Time Detection

- Load trained model
- Subscribe to MQTT topic
- Predict incoming water flow data
- If prediction = Leak:
  - Activate relay
  - Close solenoid valve
  - Trigger alert

---

## 📊 Features

- Real-time water flow monitoring
- MQTT-based IoT communication
- Machine Learning-based anomaly detection
- Automatic water shut-off system
- Edge computing with Raspberry Pi
- Remote monitoring using ngrok
- Early leak detection alerts

---

## 📈 Expected Output

- Continuous water flow monitoring
- Real-time classification (Normal / Leak)
- Automatic valve shut-off during leak
- Reduced water waste
- Improved water conservation

---

## 🔍 Applications

- Smart Homes
- Smart Buildings
- Apartment Complexes
- Industrial Water Systems

---

## 👨‍💻 Researchers

**Camila, Justine Son P.**  
**Olores, Kaye Khrysna C.**  
**Papa, Nikko P.**

Bachelor of Science in Computer Science  
Camarines Sur Polytechnic Colleges

---

## 📄 License

This project is developed for academic purposes only.
