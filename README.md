# IoT-Based-Smart-Energy-Meter


## 1.Project Overview
This project implements an IoT-based Smart Energy Meter that measures electrical parameters such as voltage, current, power, energy units, and total cost. The data is displayed locally on an I2C LCD and remotely monitored using the Blynk Web Dashboard** through Wi-Fi.
The system is built using an ESP32 microcontroller, making it suitable for smart home and energy management applications.



## 2. Components Required
* ESP32 Development Board
* ACS712 Current Sensor
* ZMPT101B Voltage Sensor Module
* 16×2 I2C LCD Display
* Breadboard
* Connecting Wires
* Load (Bulb)
* Power Supply
* USB Cable



## 3. Conceptual Block Diagram 
Load → Current Sensor → ESP32 → LCD Display & Blynk Cloud



## 4. Wiring Connections
### 4.1 Voltage Sensor to ESP32
* VCC → ESP32 VCC (3.3V / 5V as per module)
* GND → ESP32 GND
* OUT → GPIO 35 (ADC pin)

### 4.2 Current Sensor (ACS712) to ESP32
* VCC → ESP32 VCC
* GND → ESP32 GND
* OUT → GPIO 34 (ADC pin)

### 4.3 I2C LCD Display to ESP32
* VCC → ESP32 VCC
* GND → ESP32 GND
* SDA → GPIO 21
* SCL → GPIO 22

### 4.4 Load Connection
* Connect the bulb (load) in series with the current sensor
* Connect the ZMPT101B voltage sensor across the main power supply

### 4.5 Programming Connection
* Connect ESP32 to the computer using a USB cable for uploading code



## 5. Working Principle
1. The ZMPT101B voltage sensor measures the line voltage.
2. The ACS712 current sensor measures the current drawn by the load.
3. ESP32 reads analog values and calculates:
   * Voltage (V)
   * Current (A)
   * Power (W = V × I)
   * Energy Consumption (Units in kWh)
   * Total Cost (based on tariff)
4. Values are displayed on the 16×2 LCD.
5. The same data is sent to the Blynk Web Dashboard for real-time monitoring.



## 6. Blynk Web Dashboard Configuration
### 6.1 Create Blynk Template
* Go to Blynk Cloud → New Template
* Template Name: *Smart Energy Meter*
* Hardware: ESP32
* Connection Type: Wi-Fi

### 6.2 Create Datastreams (Virtual Pins)
| Parameter    | Virtual Pin | Unit        |
| ------------ | ----------- | ----------- |
| Voltage      | V0          | Volts (V)   |
| Current      | V1          | Amperes (A) |
| Power        | V2          | Watts (W)   |
| Energy Units | V3          | kWh         |
| Total Cost   | V4          | Currency    |

### 6.3 Dashboard Setup
* Add Gauge Widgets for:
  * Voltage
  * Current
  * Power
  * Energy Units
  * Total Cost
* Assign each widget to its corresponding virtual pin
* Customize labels, ranges, and colors

### 6.4 Credentials
Copy the following from Blynk:
* Template ID
* Template Name
* Auth Token
These credentials are used in the Arduino code.



## 7. Arduino IDE Setup
1. Install Arduino IDE (v2.x)
2. Install ESP32 board package
3. Install required libraries:
   * Blynk
   * LiquidCrystal_I2C
   * WiFi
4. Enter the following credentials in code
BLYNK_TEMPLATE_ID
BLYNK_TEMPLATE_NAME
BLYNK_AUTH_TOKEN
WiFi_SSID
WiFi_PASSWORD
5. Select the correct ESP32 board and COM port
6. Upload the code



## 8. Output & Results
* Real-time electrical parameters displayed on LCD
* Live monitoring via Blynk Web Dashboard
* Energy consumption and cost calculated automatically



## 9. Applications
* Smart Homes
* Energy Monitoring Systems
* Industrial Load Monitoring
* IoT-based Billing Systems



## 10. Future Enhancements
* Mobile app notifications
* Data logging and history graphs
* Relay-based load control
* Multiple load monitoring



## 11. Conclusion
This IoT-based Smart Energy Meter provides an efficient and scalable solution for monitoring electrical energy consumption in real time. Integration with ESP32 and Blynk enables remote monitoring, making it suitable for modern smart energy systems.



## 12. GitHub Repository Structure 
Smart-Energy-Meter/
│── cicuit diagram
│── code
│── README.md


## Author: G.Malleshwari 
