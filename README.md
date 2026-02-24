# Patient Health Monitoring System

An IoT-based real-time patient vital sign monitoring system built on ESP32, integrating multiple biomedical sensors and serving live health data through a web interface.

## Overview

Traditional patient monitoring requires dedicated medical equipment that is expensive and immobile. This project demonstrates a low-cost, portable alternative using commodity IoT hardware — enabling continuous monitoring of heart rate, blood oxygen saturation, body temperature, and ambient conditions via any networked device.

The system was developed as part of research into sensor network design for medical institutions, with a future roadmap toward multi-patient centralized monitoring and predictive analytics.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller + Wi-Fi web server |
| MAX30100 | Pulse oximetry and heart rate (SpO2 + BPM) |
| DS18B20 | Waterproof body temperature (-55°C to 125°C) |
| DHT11 | Ambient humidity and room temperature |
| 4.7kΩ Resistor | DS18B20 pull-up for Dallas 1-Wire protocol |
| Breadboard + Wires | Prototyping connections |

## Architecture

```
Sensors → ESP32 (data acquisition + filtering) → Wi-Fi Web Server → Browser / Mobile
```

The ESP32 reads sensor data at configurable intervals, applies filtering and anomaly detection to remove noise and invalid readings, then serves processed data via an HTTP web server hosted on the device itself. Any device on the same network can access live readings by navigating to the ESP32's IP address.

## Key Technical Details

- **Communication protocol:** Dallas 1-Wire (DS18B20), I2C (MAX30100), single-wire digital (DHT11)
- **Data processing:** Filtering algorithms and anomaly detection for reliable readings under real-world noise conditions
- **Web interface:** Real-time data visualization with alerts for abnormal vital sign thresholds
- **Power:** All sensors operate at 3.3V, directly compatible with ESP32 GPIO

## Setup & Installation

**Requirements:**
- Arduino IDE with ESP32 board support
- Libraries: `MAX30100_PulseOximeter`, `DallasTemperature`, `OneWire`, `DHT`, `ESPAsyncWebServer`

**Steps:**

1. Clone the repository:
   ```bash
   git clone https://github.com/damirzhumangali/Patient_Health_Monitoring.git
   ```

2. Open `ESP_32_Patient_Health_Monitoring.ino` in Arduino IDE

3. Configure your Wi-Fi credentials in the sketch:
   ```cpp
   const char* ssid = "YOUR_WIFI_SSID";
   const char* password = "YOUR_WIFI_PASSWORD";
   ```

4. Connect hardware according to the circuit diagram

5. Upload to ESP32 — the Serial Monitor will display the assigned IP address on successful connection

6. Navigate to the IP address in any browser on the same network

## Results

After deployment, the system streams live readings including room temperature, humidity, heart rate (BPM), blood oxygen level (SpO2), and body temperature. Patient health status is accessible from any device — including mobile — via the served IP address.

## Challenges & Engineering Decisions

The main challenge was achieving reliable readings under real-world conditions: sensor noise, timing constraints between concurrent reads, and the DHT11's 2-second minimum refresh rate required careful sequencing. Anomaly detection logic was implemented to filter out physiologically impossible values (e.g., SpO2 > 100%) before they reached the web interface.

## Future Scope

- **Multi-patient support:** Central node aggregating data from multiple ESP32 nodes across a facility
- **Additional sensors:** Blood pressure, ECG, respiratory rate, glucose
- **ML integration:** Predictive analytics and early anomaly detection
- **Security:** End-to-end encryption and HIPAA-aligned data handling
- **Cloud backend:** Long-term data storage and trend analysis

## Tech Stack

`C++` `ESP32` `Arduino IDE` `MAX30100` `DS18B20` `DHT11` `Dallas 1-Wire` `I2C` `HTTP Web Server`

## Author

**Damir Zhumangali** — [github.com/damirzhumangali](https://github.com/damirzhumangali)
