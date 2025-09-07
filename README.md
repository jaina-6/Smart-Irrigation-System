
# Smart Irrigation System

## Aim
Design a smart irrigation system to optimize water usage in agricultural fields using Cisco Packet Tracer.  
The system monitors soil moisture levels in real-time and triggers irrigation automatically when necessary.

---

## Problem Statement
Traditional irrigation methods in agriculture suffer from inefficiencies, resulting in overwatering or underwatering of crops.  
Manual irrigation does not provide real-time monitoring or automation, which leads to:
- Water wastage
- Poor crop health
- Increased labor effort

This project aims to design an automated system that monitors soil moisture and controls irrigation to optimize water usage.

---

## Scope of Solution
- Real-time monitoring of soil moisture levels using simulated IoT sensors.
- Automated triggering of a water pump when moisture is below threshold.
- Visualization of sensor data and pump status on an IoT cloud dashboard.
- Simulation of the system using Cisco Packet Tracer.
- Demonstration of network communication between devices.

---

## Required Components
- Cisco Packet Tracer (for circuit simulation)
- Soil Moisture Sensor (Simulated)
- Arduino (Simulated IoT Device)
- IoT Cloud (Packet Tracer Cloud Module)
- Water Pump (Actuator)
- Switches and Routers (Networking Components)
- Screen recording tool (e.g., OBS Studio)
- Arduino IDE (for code logic demonstration)

---

## Simulated Circuit
![Circuit Screenshot](Images/circuit_screenshot.png)

---

## Demo Video
[View Demo Video](Demo-Video.mp4)

---

## Arduino Code Example
```cpp
int moistureSensorPin = A0;
int pumpPin = 8;
int threshold = 300;

void setup() {
    Serial.begin(9600);
    pinMode(pumpPin, OUTPUT);
}

void loop() {
    int sensorValue = analogRead(moistureSensorPin);
    Serial.print("Soil Moisture: ");
    Serial.println(sensorValue);

    if (sensorValue < threshold) {
        digitalWrite(pumpPin, HIGH);  // Turn on Pump
    } else {
        digitalWrite(pumpPin, LOW);   // Turn off Pump
    }

    delay(2000);
}
