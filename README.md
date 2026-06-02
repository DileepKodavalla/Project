# A Supervised Intrusion Detection System for Smart Home IoT Devices

This repository contains the complete source code, hardware architecture, and research documentation for an advanced, dual-layered IoT Smart Home Security and Fire Safety System[cite: 1]. 

The system mitigates traditional camera "cold start" initialization latencies by utilizing an ESP32 edge microcontroller alongside a multi-threaded Python supervisor application to achieve near-instantaneous forensic image capture and transmission[cite: 1].

---

## 📂 Project Deliverables & Resources

* **📄 Published Research Paper:** [Read b2final.pdf](./b2final.pdf)[cite: 1]
* **🌐 Official Publication Link:** [View Paper on IJERT](PASTE_YOUR_IJERT_URL_HERE)
* **📊 Project Presentation:** [Download Presentation PPT](./project_presentation.pptx)
* **📋 Full Project Report:** [Read Project Report PDF](./project_report.pdf)

### 🎥 Project Demo Video
![Project Demo Video](./demo.mp4)

---

## 🛠️ System Architecture & Workflow

The project is structured across a specialized four-layer IoT framework[cite: 1]:

1. **Sensing Layer:** Employs dual HC-SR04 ultrasonic sensors for spatial intrusion detection ($<20\text{ cm}$) and an MQ-2 gas sensor for real-time smoke/fire monitoring ($>500\text{ units}$)[cite: 1].
2. **Processing Layer (Edge):** An ESP32 microcontroller continuously polls the sensors and handles immediate, local 5V Piezo buzzer and LED alarms independently of network availability[cite: 1].
3. **Supervision Layer (Host):** A high-speed Python background application maintains a "warm start" camera buffer, completely eliminating standard 2-second camera initialization delays[cite: 1]. Upon receiving a 115200-baud USB-Serial handshake trigger from the ESP32, it executes a frame-grab protocol to capture the intruder instantly[cite: 1].
4. **Cloud & Output Layer:** Conducts parallel alerting by streaming telemetry to the Blynk IoT Cloud dashboard and transmitting high-resolution forensic images to the user's smartphone via the Telegram Bot API[cite: 1].

---

## 📈 Key Performance Metrics

* **Ultra-Low Latency:** Achieves a total system response time averaging **1.16 seconds** from initial sensor trigger to visual evidence delivery on the user's phone[cite: 1].
* **High Reliability:** Attained a **98.5% accuracy rate** over 100 test cycles[cite: 1].
* **False-Positive Mitigation:** Utilizes hardware spatial filtering and analog thresholding to eliminate environmental noise while maintaining a 100% reliability rate for actual breach events[cite: 1].

---

## 📂 Repository Structure

* `/hardware_firmware` : Contains the `.ino` source code compiled via the Arduino IDE for the ESP32 edge processing[cite: 1].
* `/python_supervisor` : Contains the multi-threaded Python application script handling the serial handshake and camera frame-grab[cite: 1].
* `/documentation` : Houses the project slide deck, full report, and the published research paper[cite: 1].
