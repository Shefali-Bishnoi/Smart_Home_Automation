
# 🌐 Smart Home Automation System

## 📘 Introduction

This project integrates three critical smart home systems into a unified Arduino-based controller:

- **🏠 Home Security and Fire Detection System**  
  Monitors for unauthorized entry and fire hazards, with controlled door locking mechanisms and alarm capabilities.

- **💧 Rainwater Harvesting System**  
  Automatically collects rainwater when rain is detected and manages tank capacity.

- **💡 Motion-Activated Smart Lighting**  
  Intelligently controls lighting based on motion detection.

These systems share hardware resources and provide centralized monitoring through a serial interface, ensuring seamless operation and efficient home automation.

---

## 🎯 Motivation

The motivation behind this project stems from the following goals:

- **🔌 Resource Efficiency**  
  Combining multiple home systems on a single microcontroller reduces hardware costs and energy consumption.

- **🛡️ Safety and Security**  
  A unified system that responds to multiple threats like intrusion and fire, with real-time alarms and emergency protocols.

- **🌱 Sustainability**  
  Promotes environmental conservation by implementing rainwater harvesting and minimizing water wastage.

- **⚡ Energy Conservation**  
  Motion-activated lighting helps reduce unnecessary electricity usage.

---

## 🌟 Innovation & Uniqueness

This project stands out due to its thoughtful integration and intelligent design features:

- **🧩 Integrated Approach**  
  Combines security, safety, and resource management in a single cohesive system — unlike typical single-purpose DIY systems.

- **🚨 Emergency Intelligence**  
  Automatically unlocks doors during fire emergencies for safe evacuation.

- **🔄 Debounced Sensing**  
  Reduces false alarms by implementing debounce logic for ultrasonic and IR sensors.

- **🔐 Password Protection**  
  Multi-user code verification system for authorized access control.

- **🔁 Graceful Motion**  
  Servo motors move gradually, reducing wear and tear and offering smooth mechanical feedback.

- **⏱️ Non-Blocking Design**  
  Uses efficient programming patterns that allow concurrent operation of all subsystems without delays.

- **🌧️ Adaptive Calibration**  
  Rain detection uses threshold tuning to accommodate varying environmental conditions.

---

## 🔧 Hardware Requirements

### 🔐 Security and Fire Detection System

- Arduino board (Uno/Mega recommended)  
- Ultrasonic distance sensor (HC-SR04)  
- IR motion sensor  
- Flame sensor  
- Piezo buzzer  
- Servo motor (for door locking)  
- Red and green LEDs  
- 220Ω resistors for LEDs  

### 💦 Rainwater Harvesting System

- Analog rain sensor  
- Water level sensor  
- Servo motor (for controlling water valve)  
- Pull-up resistors (if needed)  

### 💡 Smart Lighting System

- Additional ultrasonic sensor (HC-SR04)  
- Blue LED  
- Power supply for LED/light circuit  

### 🧰 Miscellaneous

- Breadboard and jumper wires  
- 5V–9V regulated power supply for Arduino  
- USB cable or wireless module for serial communication

  ![components](https://github.com/user-attachments/assets/92f9174f-f494-4e1f-9250-03f6eb558c34)
<br>

## Flowcharts
**Main Program Loop**
![mainprogramloop](https://github.com/user-attachments/assets/ac1e10b2-1fa7-4f50-8762-e21e69beb376)
<br>
<br>
**Security System**
![security](https://github.com/user-attachments/assets/bd78c580-2168-421c-b316-fc783a15a60d)
<br>
<br>
**Rain Water Harvesting System**
![rain](https://github.com/user-attachments/assets/49aa3349-69a0-4e4c-bde3-504ffa15c14c)
<br>
<br>
**Smart Lighting System**
![SmartLighting](https://github.com/user-attachments/assets/9c78882a-99da-44a3-87a3-69ac76818f1b)
<br>




# 

**Circuit
Diagram**
![circuitdiagram](https://github.com/user-attachments/assets/4792ce2f-cfff-469d-bc14-b197b7feaeb4)


## 📦 Code Details

### 1. Security System Functions

- `initializeSecuritySystem()` – Sets up pins, servo, and initial states  
- `detectIntrusion()` – Uses ultrasonic and IR sensors to detect presence near the door  
- `promptForCode()` – Prompts for access code when someone is detected  
- `verifyAccessCode()` – Validates the entered access code  
- `unlockDoor()` – Unlocks the door upon successful verification  
- `lockDoor()` – Relocks the door after timeout or command  
- `updateServoPosition()` – Moves servo smoothly to lock/unlock position  
- `resetAwaitingCode()` – Cancels code prompt if the person leaves  
- `triggerInvalidCodeAlarm()` – Activates alarm on wrong code  
- `doubleBeep()` – Notification tone for events  
- `runSecuritySystem()` – Main coordinator for security functions

### 2. Fire Detection System Functions

- `detectFireHazard()` – Monitors flame sensor for fire detection  
- `triggerFireAlarm()` – Activates alarm and emergency mechanisms  
- `updateFireAlarm()` – Maintains alarm status and response  
- `resetFireAlarm()` – Resets alarm after fire is gone  
- `emergencyUnlock()` – Automatically unlocks door during a fire

### 3. Rainwater Harvesting System Functions

- `initializeRainwaterSystem()` – Initializes pins and servo for valve control  
- `updateRainwaterSystem()` – Uses rain sensor and water level to manage valve

### 4. Smart Lighting System Functions

- `initializeLightingSystem()` – Sets up motion detection for lighting  
- `updateLighting()` – Activates/deactivates light based on motion

---

## 🔄 Integration Flow

- `setup()` – Initializes all subsystems  
- `loop()` – Continuously calls update functions for each subsystem  
- Systems are **non-blocking** and designed to **work concurrently** without interference

---

## ✅ Project Outcome

- ✅ **Unified Home Management** – Integrated control of security, safety, and environment  
- ✅ **Reliable Intruder Detection** – Debounced multi-sensor detection system  
- ✅ **Fire Safety Measures** – Automatic alarms and emergency door unlocking  
- ✅ **Secure Access Control** – Multi-user code-based verification  
- ✅ **Water Conservation** – Rainwater harvesting with overflow prevention  
- ✅ **Energy Efficiency** – Smart lighting system based on real-time motion detection  
- ✅ **Minimal Hardware Use** – Multi-purpose sensors and actuators  
- ✅ **Non-Blocking Operation** – Efficient timing and concurrent execution

---

## 👩‍💻 Individual Contributions

### Security and Fire Detection Systems

- **Shefali Bishnoi (2301CS87)**  
  - Developed the security subsystem using ultrasonic and IR sensors  
  - Implemented access code verification and servo-controlled door locking

- **Juhi Sahni (2301CS88)**  
  - Developed the fire detection system using flame sensors  
  - Implemented emergency protocols: alarms, door unlocking, and reset functions

### Environmental Control Systems

- **Saniya Prakash (2301CS49)**  
  - Designed the rainwater system with rainfall detection and tank monitoring  
  - Automated servo-controlled water valve based on rainfall and tank status

- **Manvitha Reddy (2301CS29)**  
  - Implemented motion-based smart lighting  
  - Designed power-saving lighting logic with auto timeout

---

## 📌 Conclusion

Each subsystem was developed and tested independently, then integrated into a robust and cohesive smart home automation solution. The system demonstrates:

- Modular design
- Efficient hardware usage
- Effective team collaboration
- Seamless real-time operation

---
