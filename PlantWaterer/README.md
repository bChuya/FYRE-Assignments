# PlantWaterer - A Humidity & Moisture Structure Awning (HMSA)

## Project Overview

**PlantWaterer** is an automated environmental protection system designed to protect plants from adverse weather conditions. This device is a **Humidity & Moisture Structure Awning (HMSA)** that uses sensor-based detection to monitor environmental conditions and automatically respond to protect plant life.

The system uses an Arduino Nano ESP32 microcontroller and combines two key detection systems:

- **Humidity detection**: monitors environmental humidity using a humidity sensor
- **Moisture detection**: detects water or rain using a hand-fabricated moisture sensor and rain sensor

### How It Works

1. **Humidity Detection → Green Light Indicator**
   - When the humidity sensor detects a change in humidity, it triggers a green LED light to indicate that a change has been detected in the environment.

2. **Moisture Detection → Awning Deployment**
   - When the moisture sensor detects water, a servo motor deploys a cover that acts as an awning.
   - This protective cover helps shield the plant from rain and excess moisture.
   - If moisture is no longer detected, the awning can be retracted.

---

## Files in This Project

### 1. HomemadeSensorTest.py
**Purpose**: Tests the homemade moisture sensor to confirm it works correctly.

This script is designed to check whether the hand-fabricated moisture sensor is reading analog voltage properly and producing stable readings.

**What the code does**:
- Configures the ADC (analog input) on GPIO14, where the homemade moisture sensor is connected
- Uses a 12-bit ADC range, which means readings range from 0 to 4095
- Reads the sensor continuously in a loop
- Converts the raw ADC value into an approximate voltage using the formula:
  - voltage = (adc_value / 4095) * 3.3
- Prints a timestamp, ADC value, and voltage to the serial console every 0.25 seconds

This program is used to validate the homemade sensor before it is integrated into the larger system.

---

### 2. Test Code 1
**Purpose**: Official prototype code for the complete PlantWaterer system.

This version is the working prototype for the full humidity-moisture-awning design.

**What the code does**:
- Initializes two sensors:
  - a hand-fabricated moisture sensor on GPIO14
  - a rain sensor on GPIO3
- Uses ADC readings to monitor moisture and rain conditions in real time
- Controls a green LED on GPIO9 that turns on when moisture is detected
- Controls a servo motor on GPIO12 that moves between two positions:
  - 0° = awning retracted
  - 90° = awning deployed
- Uses threshold values to decide whether moisture or rain is present
- If the rain sensor detects water, the servo moves to 90° and deploys the cover as an awning
- If no rain or moisture is detected, the servo returns to 0°
- Includes a button on GPIO47 as a manual override to return the servo to the closed position
- Prints live sensor readings and system status messages for debugging and monitoring

This code is the official prototype control system for the full project concept.

---

## Team
Kyle, Bryan, Gabby

## Notes
- This project was created with substantial AI assistance, with manual adjustments made to sensor thresholds and servo timing
- The system is designed around Arduino Nano ESP32 hardware and uses analog sensor readings to make decisions in real time
- The hand-fabricated moisture sensor was tested separately before integration into the full prototype
