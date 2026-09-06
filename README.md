# ESP32-S3 Wi-Fi CSI Motion Detection using Arduino IDE

A real-time motion detection system developed using ESP32-S3 and
Wi-Fi Channel State Information (CSI).

The system collects CSI data, performs calibration and variance
analysis, and detects motion by comparing the measured variance
with a predefined threshold.

The project is developed and programmed using Arduino IDE.

---

## 🎯 Project Objective

The main objective of this project is to detect human motion
without using a camera.

Wi-Fi CSI signal variations are analyzed to identify changes
caused by movement in the surrounding environment.

---

## 🧩 Hardware Requirements

- ESP32-S3 × 3
- Buzzer / Audio Output
- MicroSD Card Module
- MicroSD Card
- Battery Supply
- Jumper Wires
- Push Buttons (optional)

---

## 💻 Software Requirements

- Arduino IDE
- ESP32 Board Package
- Arduino C/C++

---

## 🔄 System Flow

ESP32-S3 Nodes
        ↓
Wi-Fi CSI Data Collection
        ↓
Signal Processing
        ↓
Calibration
        ↓
Variance Calculation
        ↓
Threshold Comparison
        ↓
Motion Detection
        ↓
Audio / Buzzer Alert
        ↓
SD Card Data Logging

---

## ⚙️ Detection Method

First, the system performs calibration while the environment
is stationary.

A baseline CSI signal is obtained during calibration.

The system then continuously calculates the variation
(variance) of the incoming CSI data.

### Detection Logic

```text
Variance < Threshold
        ↓
    NO MOTION

Variance ≥ Threshold
        ↓
 MOTION DETECTED

Initial Threshold

Threshold = 3

The threshold can be adjusted after testing and calibration according to the environment.


---

📡 Multi-Node Setup

Three ESP32-S3 boards can be used as sensing nodes.

ESP32-S3
         Node 1
           │
           │ CSI / Wi-Fi
           │
        ESP32-S3
         Node 2
           │
           │ CSI / Wi-Fi
           │
        ESP32-S3
         Node 3
           │
           ↓
     Motion Processing

The multi-node configuration helps improve monitoring of the target area.


---

🔊 Audio Alert

When motion is detected, the ESP32-S3 activates the buzzer or audio output.

NO MOTION
    ↓
Buzzer OFF

MOTION DETECTED
    ↓
Buzzer / Audio ON


---

💾 SD Card Logging

Detected measurements can be stored on a MicroSD card for later analysis.

Example:

Time,Node,Variance,Threshold,Motion

10:21:01,1,1.42,3.00,NO
10:21:02,1,2.18,3.00,NO
10:21:03,1,4.76,3.00,YES


---

🛠️ Arduino IDE Setup

1. Install Arduino IDE.


2. Install the ESP32 board package.


3. Select the ESP32-S3 board.


4. Connect the ESP32-S3 using USB.


5. Open the .ino file.


6. Select the correct COM port.


7. Compile the program.


8. Upload the firmware.


9. Open Serial Monitor at the configured baud rate.


10. Start calibration and testing.




---

📁 Project Structure

ESP32-S3-WiFi-CSI-Motion-Detection/
│
├── firmware/
│   └── ESP32_CSI_Motion_Detection/
│       └── ESP32_CSI_Motion_Detection.ino
│
├── data/
│   └── sample_data.csv
│
├── docs/
│   ├── wiring.md
│   └── calibration.md
│
└── README.md


---

🧪 Calibration Procedure

1. Place the ESP32-S3 nodes in the required positions.


2. Keep the environment stationary.


3. Start the calibration process.


4. Collect CSI samples.


5. Calculate the baseline variance.


6. Set the detection threshold.


7. Introduce movement.


8. Verify the motion detection response.


9. Adjust the threshold if required.




---

📊 Output

The system provides:

CSI signal data

Variance value

Threshold value

Motion / No Motion status

Audio / Buzzer alert

SD card data logging



---

🚀 Future Improvements

Adaptive threshold

Improved noise filtering

Real-time waveform visualization

Mobile web monitoring

Battery monitoring

Multi-room monitoring

Advanced activity classification



---

📌 Project Status

Status: Under Development

Current development includes:

ESP32-S3 CSI acquisition

Calibration

Variance calculation

Threshold tuning

Motion detection

Audio alert

SD card logging



---

👩‍💻 Development Platform

Arduino IDE

Board: ESP32-S3

Language: C/C++

Detection Technology: Wi-Fi CSI

Detection Method: Variance + Threshold
