# 🏭 Smart Factory Monitoring and Safety System Using Arduino

## 📌 Project Overview

The **Smart Factory Monitoring and Safety System** is an IoT-based industrial safety monitoring project designed to improve workplace safety by continuously monitoring environmental conditions inside a factory.

Industrial environments may face several safety risks, including excessive temperature, gas leakage, and unexpected human movement in restricted areas. Delayed detection of these conditions can lead to fire hazards, gas-related accidents, equipment damage, and risks to workers.

This project uses an Arduino board integrated with an **NTC Temperature Sensor, MQ-2 Gas Sensor, and PIR Motion Sensor** to monitor factory conditions in real time. The collected sensor data is displayed on a 16×2 I2C LCD. Whenever an abnormal condition is detected, a buzzer and LED are activated to alert workers.

The system also transmits sensor readings in JSON format through Serial Communication, allowing integration with an external monitoring dashboard.

## 🎯 Problem Statement

Factories and industrial workplaces require continuous monitoring to prevent accidents caused by:
- Excessive temperature that may lead to overheating or fire hazards.
- Gas leakage and the accumulation of harmful gases.
- Unexpected human movement in restricted or hazardous areas.
- Delayed identification of unsafe environmental conditions.

Traditional monitoring methods may depend on manual inspection or separate safety devices, which can delay the detection of potential hazards.

## 💡 Proposed Solution

The proposed Smart Factory Monitoring System combines multiple sensors with an Arduino microcontroller to provide continuous environmental monitoring and immediate alerts.

The system:
- Monitors factory temperature using an NTC thermistor.
- Detects gas concentration changes using an MQ-2 gas sensor.
- Identifies movement using a PIR motion sensor.
- Displays real-time readings and safety status on an LCD.
- Activates a buzzer and warning LED when dangerous conditions are detected.
- Transmits sensor readings in JSON format through Serial Communication for external dashboard integration.

## ⚙️ Hardware Components

| Component | Purpose |
|---|---|
| Arduino Uno | Main microcontroller |
| NTC Thermistor | Temperature monitoring |
| MQ-2 Gas Sensor | Gas and smoke detection |
| PIR Motion Sensor | Human movement detection |
| 16×2 I2C LCD | Displays sensor readings and alerts |
| Buzzer | Audible warning |
| LED | Visual warning indication |
| 10KΩ Resistor | Thermistor voltage divider |
| Breadboard and Jumper Wires | Circuit connections |

## 🔌 Pin Configuration

| Component | Arduino Pin |
|---|---|
| NTC Temperature Sensor | A0 |
| MQ-2 Gas Sensor | A1 |
| PIR Motion Sensor | Digital Pin 3 |
| Buzzer | Digital Pin 6 |
| LED | Digital Pin 7 |
| I2C LCD SDA | A4 (Arduino Uno) |
| I2C LCD SCL | A5 (Arduino Uno) |

## 🔄 Working Principle

1. **Temperature Monitoring:** The NTC thermistor measures the surrounding temperature. Arduino reads the analog value and calculates the temperature in Celsius using the Beta parameter equation.

2. **Gas Detection:** The MQ-2 sensor continuously measures gas-related changes in the surrounding environment and provides an analog output.

3. **Motion Detection:** The PIR sensor detects movement in its sensing area and sends a digital HIGH signal when motion is detected.

4. **Data Processing:** Arduino processes all three sensor readings and compares them with predefined safety thresholds.

5. **LCD Display:** Temperature, gas readings, and the current safety status are displayed on the 16×2 LCD.

6. **Alert Mechanism:** When a dangerous condition is detected, the buzzer and LED turn ON to provide immediate audio and visual warnings.

7. **Serial Communication:** Sensor readings are transmitted in JSON format, enabling integration with an external IoT dashboard or monitoring system.

## 🚨 Alert Conditions

The system uses three safety levels:

| Condition | System Status | Action |
|---|---|---|
| Motion detected | DANGER | Buzzer and LED ON |
| Gas value above 700 | DANGER | Buzzer and LED ON |
| Temperature above 47°C | DANGER | Buzzer and LED ON |
| Gas value between 400 and 700 | NORMAL | No buzzer or LED |
| Temperature between 37°C and 47°C | NORMAL | No buzzer or LED |
| All readings within defined safe ranges | SAFE | No buzzer or LED |

**Note:** These are prototype thresholds, not certified industrial safety limits. MQ-2 analog readings depend on sensor calibration and environmental conditions.

## 📊 Serial Monitor Output

The system transmits sensor data in JSON format every two seconds.

Example:

```json
{
  "temperature": 32.5,
  "gas": 350,
  "motion": 0
}
```

The transmitted data can be used for external dashboard integration and remote monitoring through a compatible IoT platform or serial-to-network interface.

## 🛠️ Software and Technologies Used

- Arduino IDE
- Embedded C / Arduino Programming
- Sensor Interfacing
- Analog and Digital Input Processing
- I2C Communication
- Serial Communication
- JSON Data Formatting
- LiquidCrystal_I2C Library

## 🌍 Applications

- Manufacturing industries
- Chemical industries
- Industrial storage facilities
- Warehouses and production units
- Restricted industrial areas
- Industrial temperature and gas monitoring

## 🚀 Innovation and Key Features

- **Multi-Parameter Monitoring:** Combines temperature, gas, and motion detection in a single system.
- **Real-Time Alerts:** Provides immediate audio and visual warnings when predefined danger conditions occur.
- **Temperature Calculation:** Converts NTC thermistor resistance into temperature using the Beta equation.
- **LCD-Based Monitoring:** Displays environmental readings and safety status locally.
- **IoT Integration Potential:** Sends structured JSON data for external dashboard connectivity.
- **Cost-Effective Design:** Uses affordable and easily available electronic components.

## 🔮 Future Enhancements

- Integrate ESP32 or ESP8266 for Wi-Fi-based remote monitoring.
- Connect the system to a Blynk or cloud dashboard.
- Store historical sensor readings for analysis.
- Send mobile notifications during emergency conditions.
- Add automatic exhaust fan control when gas levels increase.
- Introduce multiple sensor nodes for monitoring different factory sections.
- Implement data logging and predictive maintenance features.

## 📌 Conclusion

The Smart Factory Monitoring and Safety System demonstrates how embedded systems and sensor technologies can be combined to improve industrial safety. By monitoring temperature, gas levels, and human movement, the system identifies potentially unsafe conditions and provides immediate alerts through a buzzer and LED.

The project offers a cost-effective prototype for smart industrial monitoring and can be further developed into a connected IoT-based factory safety solution.

## 👩‍💻 Project Category

**Domain:** Internet of Things (IoT) and Industrial Automation  
**Platform:** Arduino  
**Application:** Smart Industrial Safety and Environmental Monitoring
