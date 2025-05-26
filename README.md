🏠 Integrated Smart Home System
Integrated Smart Home System is an Arduino-based solution that unifies home security, fire detection, rainwater harvesting, and motion-activated smart lighting into a single, efficient controller. Designed for safety, sustainability, and energy conservation, this system leverages shared hardware resources and non-blocking code to provide seamless home automation.

📋 Table of Contents

Introduction
Features
Tools and Technology
Setup Instructions
Conclusion
Team


Introduction
The Integrated Smart Home System is a comprehensive Arduino-based project that combines three critical subsystems: a Home Security and Fire Detection System, a Rainwater Harvesting System, and a Motion-Activated Smart Lighting System. By integrating these functionalities into a single microcontroller, the system optimizes resource usage, enhances home safety, promotes sustainability, and reduces energy consumption. It features real-time monitoring via a serial interface and intelligent cross-system interactions, such as automatic door unlocking during fire emergencies.

Features

🔒 Home Security and Fire Detection

Detects unauthorized entry using ultrasonic and IR sensors with debounced sensing to prevent false alarms.
Implements password-protected access with multiple authorized user codes.
Monitors for fire hazards with a flame sensor, triggering alarms and emergency door unlocking.
Uses servo motors for smooth door locking/unlocking with visual feedback via LEDs.


💧 Rainwater Harvesting

Automatically collects rainwater based on analog rain sensor readings and adaptive thresholds.
Manages tank capacity with a water level sensor to prevent overflow.
Controls a servo-driven valve to open/close based on rainfall and tank status.
Provides real-time status updates via serial output.


💡 Motion-Activated Smart Lighting

Activates lighting based on motion detection using an ultrasonic sensor.
Implements a timeout mechanism to turn off lights when no motion is detected, saving energy.
Supports manual override commands via serial input for testing and control.


🔄 Non-Blocking Design

All subsystems operate concurrently without delays, ensuring smooth performance.
Shared hardware resources reduce costs and complexity.
Serial interface provides detailed debugging and status updates for all systems.


🛠 Hardware Efficiency

Utilizes a single Arduino board (e.g., Uno or Mega) to manage multiple subsystems.
Employs minimal components, including sensors, servos, LEDs, and a buzzer, connected via a breadboard.




Tools and Technology

Microcontroller: Arduino Board (e.g., Arduino Uno or Mega)
Sensors:
Ultrasonic Sensor (HC-SR04) for distance measurement
IR Motion Sensor for intrusion detection
Flame Sensor (Digital) for fire detection
Rain Sensor (Analog) for rainfall detection
Water Level Sensor for tank capacity monitoring


Actuators:
Servo Motors for door locking and valve control
Piezo Buzzer for alarms
LEDs (Red, Green, Blue) for visual feedback


Programming Language: Arduino C/C++
Hardware Components:
Breadboard and jumper wires
Resistors (220 Ω for LEDs)
Power supply for Arduino and peripherals


Development Environment: Arduino IDE
Communication: Serial interface (USB or wireless)


Setup Instructions

Hardware Setup:

Connect the components as per the pin definitions:
Security System: Ultrasonic (Trig: Pin 2, Echo: Pin 13), IR Sensor (Pin 3), Buzzer (Pin 4), Servo (Pin 5), LEDs (Red: Pin 7, Green: Pin 8), Flame Sensor (Pin A2).
Rainwater System: Rain Sensor (Pin A0), Water Level Sensor (Pin 6), Servo (Pin 9).
Smart Lighting: Ultrasonic (Trig: Pin 12, Echo: Pin A1), Blue LED (Pin 11).


Use a breadboard and jumper wires for connections.
Ensure a stable power supply for the Arduino and components.


Software Setup:

Install the Arduino IDE from arduino.cc.
Include the <Servo.h> library in your Arduino IDE.
Copy the provided code (from the report) into the Arduino IDE.
Upload the code to the Arduino board via USB.


Operation:

Open the Serial Monitor (9600 baud) to view system status and debugging output.
Enter access codes (e.g., "1234", "5678", "9012") via Serial Monitor for security system testing.
Use serial commands like lighton, lightoff, or resetmotion to control the smart lighting system.
Monitor rainwater system status and valve control through serial output.


Testing:

Test intrusion detection by approaching the ultrasonic and IR sensors.
Simulate fire detection by exposing the flame sensor to a flame source.
Test rainwater harvesting by applying water to the rain sensor and checking valve behavior.
Verify lighting system by moving within the ultrasonic sensor’s range.




Conclusion
The Integrated Smart Home System successfully delivers a unified solution for home automation, combining security, fire safety, water conservation, and energy-efficient lighting. Its non-blocking design ensures all subsystems operate seamlessly, while the use of a single Arduino board minimizes hardware costs. The system’s intelligent features, such as emergency door unlocking during fire detection and adaptive rain sensor thresholds, make it a robust and sustainable solution for modern homes.

Team

Shefali Bishnoi (2301CS87): Developed the security system, including intrusion detection and access code verification with servo-controlled door locking.
Juhi Sahni (2301CS88): Designed the fire detection system with flame sensors, emergency alarms, and automatic door unlocking.
Saniya Prakash (2301CS49): Created the rainwater harvesting system with automated valve control based on rain and tank level sensors.
Manvitha Reddy (2301CS29): Built the motion-activated smart lighting system with ultrasonic sensors and energy-saving timeout features.

