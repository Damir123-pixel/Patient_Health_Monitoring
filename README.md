Introduction
In the rapidly evolving field of healthcare technology, the Internet of Things (IoT) is playing a key role in transforming how patient health is monitored and managed. This project presents a smart patient health tracking system using a web server, enabling the monitoring of vital parameters such as heart rate, blood oxygen levels, and body temperature.

Components

ESP32 Board: 1

MAX30100 Pulse Oximeter Sensor: 1

DS18B20 Temperature Sensor: 1

DHT11 Humidity & Temperature Sensor: 1

4.7K Resistor: 1

Connecting Wires: 10

Breadboard: 1

MAX30100 Pulse Oximeter Sensor
The MAX30100 sensor integrates pulse oximetry and heart rate monitoring solutions, combining LEDs, a photodetector, optimized optics, and low-noise analog signal processing. It operates from 1.8V to 3.3V and can be powered down via software with minimal standby current.

DS18B20 Temperature Sensor
This waterproof sensor measures temperatures from -55 to 125°C. It uses the Dallas 1-Wire protocol, enabling long-distance data transmission with minimal signal degradation.

DHT11 Humidity & Temperature Sensor
The DHT11 is a low-cost digital sensor that measures temperature and humidity. It uses a capacitive humidity sensor and a thermistor, requiring precise timing for data retrieval with a refresh rate of once every 2 seconds.

Circuit Diagram
(The circuit diagram will be provided.)

Methodology

Gather the necessary components, including the ESP32, pulse oximeter sensor, and temperature and humidity sensors.

Connect the sensors to the ESP32 development board according to the wiring diagram.

Write and upload the code to the ESP32 through Arduino IDE for reading data from the sensors, displaying it on a web page, and sending it to a remote server for storage and analysis.

Test the system on the ESP32 to ensure proper functionality and sensor accuracy.

Create a user-friendly web interface for the health monitoring system, featuring real-time data visualization, alerts for abnormal readings, and historical data analysis.

Deploy the system in a real-world setting and conduct tests with actual users.

Analyze the collected data to identify trends and optimize system performance.

Continuously monitor and maintain the system to ensure data accuracy and reliability.

Implementation
The IoT-based Patient Health Monitoring system uses an ESP32 web server to interface with the sensors. The circuit diagram shows the connections of the MAX30100, DHT11, and DS18B20 sensors to the ESP32. All sensors operate at 3.3V and are connected to the power and ground pins on the ESP32.

Results and Operation
After uploading the code, the ESP32 connects to the network and displays the IP address upon successful connection. This IP address can be accessed through a web browser to view real-time data such as room temperature, humidity, heart rate, blood oxygen levels, and body temperature. The patient's health status can also be monitored via a mobile phone by accessing the provided IP address.

Future Scope: Sensor Network Design for Medical Institutions
We plan to enhance the system's capabilities to meet the needs of medical institutions by designing a comprehensive sensor network. This will include:

Central Node for Monitoring & Control via Local Cloud: A central node will aggregate data from multiple sensors deployed throughout the medical facility, enabling robust data collection and analysis.

Integration of Additional Sensors: More sensors will be added, including those for blood pressure, ECG, respiratory rate, glucose levels, and others, providing a comprehensive health monitoring solution.

Advanced Analytics and Predictive Insights: Using machine learning algorithms, actionable insights will be derived, including early detection of abnormalities and predictive analytics for disease management.

Enhanced Security and Compliance: Strong security measures will be implemented to protect patient data, ensuring compliance with regulations such as HIPAA.

Scalability and Interoperability: The system will be designed for scalability and compatibility with existing hospital management systems and medical devices.

User-Friendly Interface: The central monitoring and control interface will be intuitive, allowing healthcare professionals to make quick and informed decisions.

Commercialization and Deployment Strategy
Our commercialization strategy includes partnerships with healthcare institutions, technology providers, and regulatory bodies to ensure seamless integration and compliance. Pilot projects will validate the system's effectiveness and usability in real-world settings, with feedback informing future improvements.
