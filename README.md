# A Supervised Intrusion Detection System for Smart Home IoT Devices

This repository contains the complete source code, hardware architecture, and research documentation for an advanced, dual-layered IoT Smart Home Security and Fire Safety System[cite: 1]. 

The system mitigates traditional camera "cold start" initialization latencies by utilizing an ESP32 edge microcontroller alongside a multi-threaded Python supervisor application to achieve near-instantaneous forensic image capture and transmission.

---

## 📂 Project Deliverables & Resources

* **📄 Published Research Paper:** [Read IJERT_paper.pdf](./IJERT_paper.pdf)
* **🌐 Official Publication Link:** [View Paper on IJERT](PASTE_YOUR_IJERT_URL_HERE)
* **📊 Project Presentation:** [Download Presentation PPT](./Presentation.pptx)
* **📋 Full Project Report:** [Read Project Report PDF](./Report.pdf)

### 🎥 Project Demo Video
![Project Demo Video](./demo.mp4)

---

## 🛠️ System Architecture & Workflow

The project is structured across a specialized four-layer IoT framework:

1. **Sensing Layer:** Employs dual HC-SR04 ultrasonic sensors for spatial intrusion detection (<20cm) and an MQ-2 gas sensor for real-time smoke/fire monitoring (>500 units).
2. **Processing Layer (Edge):** An ESP32 microcontroller continuously polls the sensors and handles immediate, local 5V Piezo buzzer and LED alarms independently of network availability.
3. **Supervision Layer (Host):** A high-speed Python background application maintains a "warm start" camera buffer, completely eliminating standard 2-second camera initialization delays. Upon receiving a 115200-baud USB-Serial handshake trigger from the ESP32, it executes a frame-grab protocol to capture the intruder instantly.
4. **Cloud & Output Layer:** Conducts parallel alerting by streaming telemetry to the Blynk IoT Cloud dashboard and transmitting high-resolution forensic images to the user's smartphone via the Telegram Bot API.

---

## 📈 Key Performance Metrics

* **Ultra-Low Latency:** Achieves a total system response time averaging **1.16 seconds** from initial sensor trigger to visual evidence delivery on the user's phone.
* **High Reliability:** Attained a **98.5% accuracy rate** over 100 test cycles.
* **False-Positive Mitigation:** Utilizes hardware spatial filtering and analog thresholding to eliminate environmental noise while maintaining a 100% reliability rate for actual breach events.

---
