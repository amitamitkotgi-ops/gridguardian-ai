# GridGuardian AI

## Smart Solar Battery Management System

GridGuardian AI is an IoT-based smart solar battery management and energy monitoring system designed to monitor the performance and health of a 12V solar battery system.

The project combines embedded systems, electronics, IoT, web technologies, data visualization, and future TinyML capabilities into a single monitoring platform.

The main goal of the project is to provide a clear and user-friendly dashboard where important battery parameters such as voltage, current, power, temperature, and state of charge can be monitored.

---

## Project Overview

Solar energy systems require continuous monitoring to ensure that the battery is operating safely and efficiently.

GridGuardian AI provides a digital monitoring interface for a solar-powered battery system. Sensor data can be collected using an ESP32 microcontroller and displayed on a web dashboard.

The current version of the dashboard operates in **Simulation Mode**, where realistic sensor values are generated using JavaScript.

The next stage of development will connect the dashboard to real ESP32 hardware and Firebase for live IoT monitoring.

In the future, TinyML techniques can be integrated into the ESP32 system to detect abnormal battery behavior, electrical faults, and energy-related anomalies.

---

## Objectives

The main objectives of GridGuardian AI are:

- Monitor 12V solar battery parameters.
- Measure battery voltage and current.
- Calculate and display power consumption.
- Monitor battery temperature.
- Estimate battery State of Charge (SOC).
- Display charging and idle conditions.
- Provide real-time data visualization.
- Create a user-friendly web dashboard.
- Provide device health information.
- Generate smart alerts for abnormal conditions.
- Control electrical loads using a relay.
- Connect the system to ESP32 hardware.
- Store and monitor data using Firebase.
- Explore TinyML for future fault and anomaly detection.

---

## System Architecture

The planned system follows this architecture:

Solar Panel
        ↓
Solar Charge Controller
        ↓
12V Battery
        ↓
Voltage Sensor + Current Sensor + Temperature Sensor
        ↓
ESP32
        ↓
Wi-Fi
        ↓
Firebase
        ↓
Web Dashboard

The ESP32 acts as the main controller and collects information from the connected sensors.

The collected data can be transmitted through Wi-Fi to Firebase and displayed on the web dashboard.

---

## Hardware Components

### ESP32

The ESP32 is used as the main microcontroller of the system.

It provides:

- Sensor interfacing
- Data processing
- Wi-Fi connectivity
- Relay control
- Future TinyML processing
- Communication with Firebase

### Solar Panel

A 20W solar panel is used as the renewable energy source for the system.

It provides electrical energy that can be used to charge the 12V battery through the solar charge controller.

### 12V Battery

A 12V 7Ah battery is used as the energy storage unit.

The system monitors its voltage, current, temperature, and estimated State of Charge.

### Solar Charge Controller

The solar charge controller manages the charging process between the solar panel and the battery.

It helps protect the battery from improper charging conditions.

### Voltage Sensor

The voltage sensing circuit is used to measure the battery voltage.

The measured voltage can be processed by the ESP32 and used for battery monitoring and State of Charge estimation.

### ACS712 Current Sensor

The ACS712 current sensor is used to measure the current flowing through the system.

Current measurements can be combined with voltage measurements to estimate electrical power.

### Temperature Sensor

A temperature sensor is used to monitor the operating temperature of the battery/system.

Temperature information can be useful for detecting abnormal operating conditions.

### OLED Display

An OLED display can be used to show important values locally, such as:

- Battery Voltage
- Current
- Power
- Temperature
- Battery SOC
- System Status

### Relay Module

A relay module is used to control an electrical load.

The ESP32 can control the relay based on system conditions or user commands from the dashboard.

### Buzzer

A buzzer can provide an audible warning when an abnormal condition or alert is detected.

### LM2596 Buck Converter

The LM2596 buck converter can be used to regulate the voltage required by low-voltage electronics from the battery supply.

---

## Software Technologies

The project uses the following technologies:

- HTML5
- CSS3
- JavaScript
- Tailwind CSS
- Chart.js
- ESP32
- Firebase
- TinyML

Some technologies such as Firebase and TinyML are planned for future stages of the project.

---

## Web Dashboard

The GridGuardian AI dashboard is designed to provide a simple and clear overview of the solar battery system.

The dashboard can display:

### Battery Voltage

Shows the current battery voltage and helps understand the battery operating condition.

### Current

Displays the electrical current being measured by the current sensor.

### Power

Power can be calculated using:

Power = Voltage × Current

### Temperature

Displays the measured system or battery temperature.

### State of Charge

The dashboard provides an estimated battery State of Charge (SOC).

### Charging Status

The system can indicate whether the battery is currently charging or in an idle condition.

### Device Health

The dashboard can display the health/status of connected devices and sensors.

### Live Charts

Chart.js is used to visualize changing sensor values over time.

This makes it easier to understand battery behavior instead of looking only at individual numbers.

---

## Simulation Mode

The current dashboard operates in Simulation Mode.

Since the physical ESP32 hardware and sensors are not connected to the dashboard yet, JavaScript generates realistic sensor values.

The simulator provides changing values for parameters such as:

- Voltage
- Current
- Temperature
- State of Charge
- Charging status

This allows the complete dashboard interface to be developed and tested before connecting the physical hardware.

The simulation layer is designed so that it can later be replaced by real ESP32 and Firebase data.

---

## Planned IoT Implementation

The future IoT version will connect the physical hardware to the web dashboard.

The expected data flow is:

Sensors
        ↓
ESP32
        ↓
Wi-Fi
        ↓
Firebase Realtime Database
        ↓
Web Dashboard

The ESP32 will read sensor values and transmit them to Firebase.

The web dashboard will retrieve the latest values and display them in real time.

---

## TinyML Integration

TinyML is planned as a future enhancement of GridGuardian AI.

The objective is to use machine learning models on resource-constrained embedded hardware such as the ESP32.

The model could analyze sensor patterns and identify abnormal behavior.

Possible applications include:

- Battery fault detection
- Abnormal current detection
- Voltage anomaly detection
- Temperature anomaly detection
- Energy usage anomaly detection
- Possible energy theft detection

TinyML is currently a planned feature and will be implemented and tested separately before being considered part of the completed hardware system.

---

## Smart Alerts

The dashboard can provide alerts when monitored values move outside expected ranges.

Example conditions include:

- High battery temperature
- Abnormal voltage
- Excessive current
- Low battery SOC
- Sensor problems
- Device connection problems

The alert system can help the user quickly identify conditions that require attention.

---

## Relay Control

A relay module can be controlled through the ESP32.

The web dashboard can provide a control interface for switching a connected load ON or OFF.

In the future, automatic control logic can also be implemented based on battery conditions.

For example:

Low Battery
        ↓
Protection Logic
        ↓
Relay Control
        ↓
Load Disconnected

This can help prevent excessive battery discharge.

---

## Project Development Stages

### Stage 1 — Dashboard Simulation

Current development stage:

- Web dashboard
- JavaScript simulation
- Battery monitoring interface
- Live charts
- Status indicators
- Smart alerts
- Relay control interface

### Stage 2 — Real Hardware

Planned:

- ESP32
- Voltage sensor
- ACS712 current sensor
- Temperature sensor
- OLED display
- Relay
- Buzzer
- Solar panel
- Battery

### Stage 3 — IoT Connectivity

Planned:

ESP32
        ↓
Wi-Fi
        ↓
Firebase
        ↓
Web Dashboard

### Stage 4 — TinyML

Planned:

Sensor Data
        ↓
ESP32
        ↓
TinyML Model
        ↓
Anomaly / Fault Detection
        ↓
Alert
        ↓
Dashboard

---

## Physical Model

The planned physical prototype includes:

- 20W solar panel
- 12V 7Ah battery
- ESP32 development board
- Solar charge controller
- Voltage sensing circuit
- ACS712 current sensor
- Temperature sensor
- OLED display
- Relay module
- Buzzer
- LM2596 buck converter

Approximate prototype dimensions:

**28 cm × 18 cm**

The physical model is designed to demonstrate the complete concept of solar energy generation, battery storage, sensing, embedded control, and digital monitoring.

---

## Key Features

- Real-time battery monitoring
- Voltage measurement
- Current measurement
- Power calculation
- Temperature monitoring
- Battery SOC estimation
- Charging/Idle indication
- Web-based dashboard
- Live data visualization
- Smart alerts
- Relay control
- Device health monitoring
- ESP32 integration
- Firebase integration planned
- TinyML integration planned
- Simulation mode for development

---

## Applications

GridGuardian AI can be useful for:

- Solar battery monitoring
- Renewable energy systems
- IoT-based energy monitoring
- Embedded systems projects
- Battery management experiments
- Smart energy systems
- Educational demonstrations
- Future anomaly detection systems

---

## Future Improvements

Future versions of the project can include:

1. Real ESP32 sensor integration.
2. Firebase Realtime Database connectivity.
3. Historical sensor data storage.
4. Energy consumption reports.
5. Data export functionality.
6. Mobile-friendly dashboard.
7. User authentication.
8. Multiple device monitoring.
9. Advanced battery State of Charge estimation.
10. TinyML-based fault detection.
11. Energy anomaly detection.
12. Automated protection logic.
13. Improved battery health estimation.
14. Remote device monitoring.

---

## Learning Outcomes

Through this project, the following concepts can be explored:

- Embedded systems
- ESP32 programming
- Sensor interfacing
- Voltage measurement
- Current measurement
- Temperature sensing
- Battery monitoring
- Solar energy systems
- IoT communication
- Firebase
- Web development
- JavaScript
- Data visualization
- Chart.js
- Relay control
- Embedded machine learning
- TinyML
- Fault detection
- System integration

---

## Project Status

**Current Status: Simulation Mode**

The web dashboard and simulation environment are being developed first.

Real hardware integration with ESP32, sensors, Firebase, and TinyML will be developed in future stages.

---

## Conclusion

GridGuardian AI combines solar energy, battery monitoring, embedded systems, IoT, web technology, and future TinyML capabilities into one engineering project.

The project is designed to evolve from a browser-based simulation into a real-world ESP32-based solar battery monitoring system.

The long-term goal is to create a system capable of not only monitoring energy and battery parameters but also identifying abnormal conditions using intelligent data analysis.

---

## Author

**Amit**

Electronics & Communication Engineering

Interests:
- Embedded Systems
- IoT
- Electronics
- Energy Systems
- ESP32
- Machine Learning
- TinyML

---

## Technologies

`ESP32` `IoT` `Solar Energy` `Battery Management` `JavaScript` `HTML5` `Tailwind CSS` `Chart.js` `Firebase` `TinyML` `Embedded Systems`

---

## Project License

This project is created for educational, engineering, and portfolio purposes.
