IoT Based Telegram Security Bot

Author: Pranoy Mukherjee

Institution: Sant Longowal Institute of Engineering And Technology (SLIET)

📌 Project Overview

This project is an IoT-based security system designed to detect motion and send instant real-time alerts to a user's smartphone via Telegram. Built using the NodeMCU ESP8266 and a PIR Motion Sensor, it offers a cost-effective, energy-efficient, and scalable solution for home, office, or agricultural security.

✨ Features

Real-time Monitoring: Continuous surveillance of the designated area.

Instant Alerts: Sends a "Motion Detected!!" notification to your Telegram immediately upon detection.

Remote Access: Monitor security status from anywhere using the Telegram app.

Wireless Connectivity: Utilizes Wi-Fi (ESP8266) for communication.

Low Cost & Energy Efficient: Uses affordable components suitable for battery operation.

🛠️ Hardware Requirements

NodeMCU ESP8266: Wi-Fi enabled microcontroller unit.

HC-SR501 PIR Sensor: Passive Infrared sensor for motion detection.

Jumper Wires: For connections.

Power Supply: 5V DC (Micro USB or external battery).

💻 Software & Libraries

The code is written in C++ using the Arduino IDE. The following libraries are required:

ESP8266WiFi: For Wi-Fi connectivity.

WiFiClientSecure: For secure HTTPS connection to Telegram API.

ArduinoJson: Required for parsing API responses.

UniversalTelegramBot: By Brian Lough (Handles Telegram API interactions).

⚙️ Circuit Connection

PIR Sensor VCC -> NodeMCU Vin/3.3V

PIR Sensor GND -> NodeMCU GND

PIR Sensor OUTPUT -> NodeMCU D5 (GPIO 14) * (As defined in the code)*

🚀 Setup Guide

Step 1: Create a Telegram Bot

Open Telegram and search for @BotFather.

Send the command /newbot.

Follow instructions to name your bot.

Copy the HTTP API Token provided (you will need this for the code).

Step 2: Get Your Chat ID

Search for @IDBot on Telegram.

Send the command /getid.

Copy your User ID (this ensures the bot sends alerts only to you).

Step 3: Configure the Code

Open the Arduino sketch and update the following lines with your credentials:

const char* ssid = "YOUR_WIFI_SSID";          // Enter your Wi-Fi Name
const char* password = "YOUR_WIFI_PASSWORD";  // Enter your Wi-Fi Password

#define BOTtoken "YOUR_BOT_TOKEN_HERE"        // Token from BotFather
#define CHAT_ID "YOUR_USER_ID_HERE"           // ID from IDBot


Compile LaTeX Code

Step 4: Uploading

Select the board: NodeMCU 1.0 (ESP-12E Module).

Connect the NodeMCU to your PC.

Upload the sketch via Arduino IDE.

🧠 How It Works

The PIR sensor continuously scans for infrared radiation changes (motion).

When motion is detected, the sensor sends a HIGH signal to GPIO 14.

This triggers an interrupt function detectsMovement() in the code.

The NodeMCU connects to the Telegram Bot API via Wi-Fi.

A message "Motion detected!!" is pushed to the specified Chat ID.

📜 License & Credits

Project developed by Pranoy Mukherjee under the Department of Mechanical Engineering, SLIET.
