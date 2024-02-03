
# ESP8266-WITH-MOTION-SENSOR

Certainly! The ESP8266 is a popular Wi-Fi module that can be programmed using the Arduino IDE. If you want to create a program that involves an ESP8266 and a motion sensor, you'll need to connect the motion sensor to the ESP8266 and write a program to handle the sensor data.

Here's a basic example using the Arduino IDE:

1.Hardware Setup:

Connect the motion sensor to the ESP8266. Usually, motion sensors have three pins: VCC, GND, and OUT. Connect VCC to a 3.3V pin on the ESP8266, GND to GND, and OUT to any digital pin (e.g., D2).
Arduino IDE Setup:

Make sure you have the Arduino IDE installed and set up for ESP8266 development. You can follow the instructions provided by the Arduino ESP8266 core.
Code:

Create a new Arduino sketch and use the following code as a starting point:
// Include necessary libraries
#include <ESP8266WiFi.h>

// Replace with your network credentials
const char *ssid = "your-SSID";
const char *password = "your-PASSWORD";

// Pin connected to the motion sensor
const int motionSensorPin = D2; // Change D2 to the pin you connected the motion sensor to

void setup() {
  Serial.begin(115200);

  // Connect to Wi-Fi
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }
  Serial.println("Connected to WiFi");

  // Initialize motion sensor pin
  pinMode(motionSensorPin, INPUT);
}

void loop() {
  // Read motion sensor value
  int motionValue = digitalRead(motionSensorPin);

  if (motionValue == HIGH) {
    Serial.println("Motion detected!");
    // Perform actions when motion is detected, e.g., send an alert
  }

  delay(1000); // Adjust delay as needed
}
Certainly! The ESP8266 is a popular Wi-Fi module that can be programmed using the Arduino IDE. If you want to create a program that involves an ESP8266 and a motion sensor, you'll need to connect the motion sensor to the ESP8266 and write a program to handle the sensor data.

Here's a basic example using the Arduino IDE:

1. **Hardware Setup:**
   - Connect the motion sensor to the ESP8266. Usually, motion sensors have three pins: VCC, GND, and OUT. Connect VCC to a 3.3V pin on the ESP8266, GND to GND, and OUT to any digital pin (e.g., D2).

2. **Arduino IDE Setup:**
   - Make sure you have the Arduino IDE installed and set up for ESP8266 development. You can follow the instructions provided by the [Arduino ESP8266 core](https://github.com/esp8266/Arduino).

3. **Code:**
   - Create a new Arduino sketch and use the following code as a starting point:

```cpp
// Include necessary libraries
#include <ESP8266WiFi.h>

// Replace with your network credentials
const char *ssid = "your-SSID";
const char *password = "your-PASSWORD";

// Pin connected to the motion sensor
const int motionSensorPin = D2; // Change D2 to the pin you connected the motion sensor to

void setup() {
  Serial.begin(115200);

  // Connect to Wi-Fi
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }
  Serial.println("Connected to WiFi");

  // Initialize motion sensor pin
  pinMode(motionSensorPin, INPUT);
}

void loop() {
  // Read motion sensor value
  int motionValue = digitalRead(motionSensorPin);

  if (motionValue == HIGH) {
    Serial.println("Motion detected!");
    // Perform actions when motion is detected, e.g., send an alert
  }

  delay(1000); // Adjust delay as needed
}
```

4. **Customization:**
   - Replace "your-SSID" and "your-PASSWORD" with your Wi-Fi network credentials.
   - Modify the `motionSensorPin` to match the pin you connected the motion sensor to.
   - Add any specific actions you want to perform when motion is detected within the `if (motionValue == HIGH)` block.

5. **Upload:**
   - Connect your ESP8266 to your computer and upload the code using the Arduino IDE.

This is a basic example, and you can expand upon it based on your specific requirements. Depending on the motion sensor, you might need to adjust the code to handle its output correctly. Additionally, consider incorporating a library if your motion sensor requires one.
