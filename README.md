#  IoT Temperature Monitoring & Anomaly Detection System (Wokwi Simulation)

##  Overview
This project demonstrates a smart IoT-based temperature and humidity monitoring system using an ESP32 and DHT22 sensor. The system processes real-time sensor data, applies signal smoothing (EWMA), and performs anomaly detection.

The entire system is developed and tested in the Wokwi simulation environment, making it easy to reproduce without physical hardware while still reflecting real embedded system behavior.

---

##  Project Objectives
- Monitor environmental temperature and humidity
- Reduce sensor noise using filtering techniques
- Detect abnormal temperature variations
- Transmit data using MQTT protocol
- Simulate a complete IoT pipeline using Wokwi

---

##  System Workflow
[DHT22 Sensor] → [ESP32 Processing] → [EWMA Filter] → [Anomaly Detection] → [MQTT Broker]

---

##  Technologies & Tools
- ESP32 (Simulated in Wokwi)
- DHT22 Temperature & Humidity Sensor
- WiFi Communication
- MQTT Protocol (HiveMQ Public Broker)
- Arduino Framework (C/C++)
- Wokwi Online Simulator

---

##  Key Features

###  WiFi Connectivity
- Connects to `Wokwi-GUEST`
- Handles connection reliability

### Real-Time Sensor Monitoring
- Reads temperature and humidity from DHT22
- Handles invalid or missing readings

###  EWMA Filtering
Implements Exponential Weighted Moving Average:

EWMA = α × T + (1 - α) × EWMA_previous

- Smoothing factor (α) = 0.2  
- Reduces noise and stabilizes readings

###  Anomaly Detection
- Detects sudden temperature changes
- Threshold margin: ±2.5°C
- Publishes alert via MQTT when anomaly is detected

### 📤 MQTT Data Publishing
Data is sent to the following topics:

zubair/iot/temp  
zubair/iot/hum  
zubair/iot/ewma  
zubair/iot/alert  

---

##  System Timing
- Sensor update interval: 3 seconds  
- MQTT reconnect interval: 5 seconds  

---

##  Simulation Details (Wokwi)
- Platform: https://wokwi.com/
- Board: ESP32
- Sensor: DHT22
- Network: Simulated WiFi environment
- [demo](https://wokwi.com/projects/461035964742253569)

Note: This project is fully implemented and tested in Wokwi (simulation only).  
However, the same code can be deployed on real ESP32 hardware with minimal changes.

---

##  Sample Output
Temp: 30.10  
EWMA: 29.20  
Threshold: 31.70  
----------------------  
⚠ ANOMALY DETECTED  

---

## How to Run the Project

1. Open https://wokwi.com/
2. Create a new ESP32 project
3. Add a DHT22 sensor
4. Copy and paste the code into `main.cpp`
5. Start the simulation
6. Open Serial Monitor to view output

---

##  MQTT Testing (Optional)

- Broker: broker.hivemq.com  
- Port: 1883  

Subscribe to topics:

zubair/iot/temp  
zubair/iot/hum  
zubair/iot/ewma  
zubair/iot/alert  

---
## Author
Zubair Iqbal  
BS ELECTRONICS  
Government College University Lahore  
