# IoT-Based Plant Monitoring System

The **IoT-Based Plant Monitoring System** is a smart solution designed to automate and optimize plant care using **IoT devices and sensors**. This project is ideal for **home gardeners, agricultural professionals**, or anyone interested in enhancing their **plant care routine with technology**.

---

## Features

- **Soil Moisture Monitoring:** Tracks soil moisture levels to ensure plants receive the right amount of water.  
- **Temperature & Humidity Monitoring:** Uses a **DHT11 sensor** to provide real-time environmental feedback.  
- **Motion Detection:** A **PIR motion sensor** detects movement near plants, enhancing garden security.  
- **LCD Display:** Displays live data for **temperature, humidity, and soil moisture**.  
- **Blynk Integration:** Enables remote monitoring and control via the **Blynk app**.  
- **Relay Control:** Operates external devices like **irrigation systems or lights** based on conditions or manual commands.  
- **Physical Button Input:** Allows local manual relay control for added convenience.  

---

## Components & Requirements

### Hardware  
- **ESP8266 NodeMCU** – Microcontroller for managing sensors & Wi-Fi.  
- **DHT11 Sensor** – Measures temperature & humidity.  
- **Soil Moisture Sensor** – Monitors soil moisture levels.  
- **PIR Sensor** – Detects motion in the plant area.  
- **Relay Module** – Controls external devices (e.g., water pump, grow light).  
- **Push Button** – Provides manual control over the relay.  
- **16x2 LCD Display with I2C Module** – Displays real-time sensor data.  

### Software  
- **Arduino IDE** – For code development & uploading.  
- **Blynk App** – For remote monitoring & control.  

### Required Libraries  
Install these libraries via the **Arduino Library Manager** or download them manually:  

LiquidCrystal_I2C
ESP8266WiFi
BlynkSimpleEsp8266
DHT



---

## Getting Started  

### 1. Install Required Libraries  
Ensure the necessary **Arduino libraries** are installed:  

LiquidCrystal_I2C
ESP8266WiFi
BlynkSimpleEsp8266
DHT



### 2. Connect the Components  
Refer to the **circuit diagram** for connecting:  
- **DHT11 Sensor**  
- **Soil Moisture Sensor**  
- **PIR Sensor**  
- **LCD Display**  
- **Relay Module**  
- **Push Button**  

### 3. Setup Blynk  
1. Download the **Blynk App**.  
2. Create a **new project** in the app and copy the **authentication token**.  
3. Set up **virtual pins** in the app:  
   - **V6** → Toggles PIR sensor.  
   - **Other Virtual Pins** → For push button & relay control.  

### 4. Update Wi-Fi Credentials  
Replace placeholders with your actual Wi-Fi credentials in the code:  

```cpp
char auth[] = "YourAuthToken";
char ssid[] = "YourWiFiSSID";
char pass[] = "YourWiFiPassword";

5. Upload the Code
Upload the provided code to the ESP8266 NodeMCU using the Arduino IDE.

6. Power On
Power the ESP8266 and monitor the system via the LCD display and Blynk app.

Code Explanation
Libraries and Initial Setup
The project uses the following libraries:

LiquidCrystal_I2C for LCD control
ESP8266WiFi and BlynkSimpleEsp8266 for Wi-Fi and Blynk integration
DHT for temperature and humidity readings
Global Variables
Wi-Fi credentials (auth, ssid, pass) for Blynk connectivity
Sensor pins for soil moisture and PIR sensors
States for relay and physical button
Setup
Initializes all components (LCD, DHT sensor, Wi-Fi)
Sets up the Blynk connection and schedules periodic tasks for reading sensor data
Sensor Functions
DHT11 Sensor:
Reads temperature and humidity values
Sends data to the Blynk app and displays it on the LCD
Soil Moisture Sensor:
Maps soil moisture raw data to a percentage
Sends moisture level to Blynk and displays it on the LCD
PIR Sensor:
Detects motion and logs events to Blynk
Blynk Functions
Syncs the PIR sensor and relay states with the app
Updates relay state when toggled via the app
Physical Button
Monitors the state of the push button to toggle the relay locally
Main Loop
Continuously updates the LCD with sensor data
Manages tasks through Blynk and timers
How It Works
Data Collection: Sensors gather data about temperature, humidity, and soil moisture.
Real-Time Display: Sensor data is displayed on the LCD and sent to the Blynk app.
Automation: The relay can be controlled based on sensor readings or manually through the app or push button.
Motion Alerts: The PIR sensor detects motion and alerts the user via the Blynk app.
Future Enhancements
Add support for more sensors (e.g., light intensity)
Implement advanced automation rules
Enable data logging for long-term analysis
Integrate with other IoT platforms
