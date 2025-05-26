# [Smart Home]{.underline}

# Report By -- Shefali Bishnoi(2301CS87), Juhi Sahni(2301CS88), Saniya Prakash(2301CS49), Manvitha Reddy(2301CS29)

# Introduction

This project integrates three critical smart home systems into a unified
Arduino-based controller:

1.  **Home Security and Fire Detection System**: Monitors for
    unauthorized entry and fire hazards, with controlled door locking
    mechanisms and alarm capabilities.

2.  **Rainwater Harvesting System**: Automatically collects rainwater
    when rain is detected and manages tank capacity.

3.  **Motion-Activated Smart Lighting**: Intelligently controls lighting
    based on motion detection.

The integration allows these systems to work together seamlessly while
sharing hardware resources and providing centralized monitoring through
a serial interface.

# Motivation

The motivation for this project stems from several factors:

-   **Resource Efficiency**: Combining multiple home management systems
    on a single microcontroller reduces hardware costs and power
    consumption.

-   **Safety and Security**: Creating an integrated approach to home
    safety that addresses multiple threats simultaneously (intrusion,
    fire) while providing emergency responses.

-   **Sustainability**: Implementing rainwater harvesting to promote
    environmental conservation and reduce water consumption.

-   **Energy Conservation**: Using motion detection for lighting control
    to minimize electricity usage.

# Innovation/Uniqueness

The project stands out in several ways:

1.  **Integrated Approach**: Unlike most DIY solutions that focus on a
    single aspect of home automation, this system combines security,
    safety and resource management in one circuit.

2.  **Emergency Intelligence**: The system features cross-functional
    emergency protocols, such as automatically unlocking doors when a
    fire is detected.

3.  **Debounced Sensing**: Implements sophisticated sensor debouncing
    techniques to prevent false alarms from ultrasonic and IR sensors.

4.  **Password Protection**: Incorporates a code verification system
    with multiple authorized users.

5.  **Graceful Motion**: Servo motors move gradually rather than
    abruptly, extending component life and providing visual feedback.

6.  **Non-Blocking Design**: The entire system operates without blocking
    delays, allowing all systems to run concurrently.

7.  **Adaptive Calibration**: The rainwater sensor uses adaptive
    thresholds to accommodate different environmental conditions.

# Hardware Requirements

**Security and Fire Detection System**

-   Arduino board (e.g., Arduino Uno or Mega)

-   Ultrasonic distance sensor (HC-SR04)

-   IR motion sensor

-   Flame sensor

-   Piezo buzzer

-   Servo motor (for door lock)

-   Red and green LEDs

-   Resistors for LEDs (220Ω)

**Rainwater Harvesting System**

-   Rain sensor (analog)

-   Water level sensor

-   Servo motor (for valve control)

-   Resistors for pull-up (if needed)

**Smart Lighting System**

-   Additional ultrasonic sensor (HC-SR04)

-   Blue LED

-   Power supply for lights

**Miscellaneous**

-   Breadboard and jumper wires

-   Power supply for Arduino

-   Serial communication interface (USB or wireless)

  -----------------------------------------------------------------------
  Component Name                                   Quantity
  ------------------------------------------------ ----------------------
  Arduino Board (e.g., Uno)                        **1**

  Ultrasonic Sensor                                **2**

  IR Sensor                                        **1**

  Buzzer                                           **1**

  Servo Motor                                      **2**

  LED (Red)                                        **1**

  LED (Green)                                      **1**

  LED (Blue)                                       **1**

  Flame Sensor (Digital)                           **1**

  Rain Sensor (Analog)                             **1**

  Water Level Sensor                               **1**

  Breadboard                                       **1**
  -----------------------------------------------------------------------

# Flowcharts

![](vertopal_2dced53eb96a47d5907fc82e53fc933f/media/image1.png){width="4.6in"
height="3.441666666666667in"}

![](vertopal_2dced53eb96a47d5907fc82e53fc933f/media/image2.png){width="3.7756944444444445in"
height="5.405555555555556in"}![](vertopal_2dced53eb96a47d5907fc82e53fc933f/media/image3.png){width="3.6506944444444445in"
height="5.447222222222222in"}

![](vertopal_2dced53eb96a47d5907fc82e53fc933f/media/image4.png){width="8.097248468941382in"
height="6.838542213473316in"}**[Security System]{.underline}**

# 

**Circuit
Diagram**![](vertopal_2dced53eb96a47d5907fc82e53fc933f/media/image5.png){width="6.933847331583552in"
height="5.234375546806649in"}

# Code Details

The code is organized into three main subsystems that share the
Arduino\'s resources:

1.  [Security System:]{.underline} Handles intrusion detection, fire
    detection, and door locking mechanisms.

2.  [Rainwater System]{.underline}: Manages rain detection and water
    valve control.

3.  [Smart Lighting System:]{.underline} Controls lighting based on
    motion detection.

Each system has its own initialization function, update function, and
dedicated set of pins. The systems operate independently but can
influence each other, such as when the fire detection system triggers
the emergency door unlock mechanism. Code has following functions:

1.  **Security System Functions**

-   [initializeSecuritySystem()]{.underline}: Sets up pins, servo, and
    initial states for the security system

-   [detectIntrusion():]{.underline} Uses ultrasonic and IR sensors to
    detect if someone is near the door

-   [promptForCode():]{.underline} Requests an access code when a person
    is detected

-   [verifyAccessCode():]{.underline} Checks if entered code matches
    authorized codes

-   [unlockDoor():]{.underline} Opens the door when access is granted

-   [lockDoor():]{.underline} Re-locks the door after timeout or on
    command

-   [updateServoPosition():]{.underline} Gradually moves the door lock
    servo to target position

-   [resetAwaitingCode():]{.underline} Cancels code request if no person
    is detected anymore

-   [triggerInvalidCodeAlarm():]{.underline} Activates alarm when
    incorrect code is entered

-   [doubleBeep():]{.underline} Produces notification sound for various
    security events

-   [runSecuritySystem():]{.underline} Main function that coordinates
    security operations

2.  **Fire Detection System Functions**

-   [detectFireHazard():]{.underline} Checks flame sensor for fire
    detection

-   [triggerFireAlarm():]{.underline} Activates alarm and emergency
    procedures when fire is detected

-   [updateFireAlarm():]{.underline} Manages ongoing fire alarm state
    and responses

-   [resetFireAlarm():]{.underline} Turns off alarm when fire is no
    longer detected

-   [emergencyUnlock():]{.underline} Automatically unlocks door during
    fire emergency

3.  **Rainwater Harvesting System Functions**

-   [initializeRainwaterSystem():]{.underline} Sets up pins and servo
    for rainwater system

-   [updateRainwaterSystem():]{.underline} Checks rain sensor and water
    tank level to control valve

4.  **Smart Lighting System Functions**

-   [initializeLightingSystem():]{.underline} Sets up pins for
    motion-activated lighting

-   [updateLighting():]{.underline} Detects motion and controls lights
    based on presence

Each subsystem works independently but is integrated into the main
program flow, with setup() initializing all systems and loop() running
them continuously.

Project Outcome

The integrated smart home system successfully achieved the following
results:

1.  **Unified Home Management**: Created a single system that handles
    security, safety, resource management, and convenience features.

2.  **Reliable Detection**: The security system can detect intruders
    using multiple sensors with debouncing to minimize false alarms.

3.  **Fire Safety**: The system can detect fire hazards and
    automatically unlock doors for emergency evacuation while activating
    alarms.

4.  **Access Control**: Implemented a multi-user code verification
    system for authorized entry.

5.  **Water Conservation**: Created an automated rainwater harvesting
    system that collects water when it rains and prevents overflow.

6.  **Energy Efficiency**: Implemented motion-activated lighting that
    only operates when needed.

7.  **Hardware Economy**: Achieved multiple home automation functions
    with minimal hardware through efficient integration.

8.  **Non-Blocking Operation**: All systems operate concurrently without
    interfering with each other through proper timing management.

# Individual Contributions

**Security and Fire Detection Systems**

-   **[Shefali Bishnoi (2301CS87):]{.underline}** Developed the security
    system with ultrasonic and IR sensor integration for intrusion
    detection. Implemented the access code verification system and door
    locking mechanism with servo control for authorized entry.

-   **[Juhi Sahni (2301CS88):]{.underline}** Created the fire detection
    system using flame sensors to monitor for fire hazards. Implemented
    emergency protocols including alarm triggering, automatic door
    unlocking during fire emergencies, and reset functionality when fire
    is no longer detected.

**Environmental Control Systems**

-   **[Saniya Prakash (2301CS49):]{.underline}** Designed the rainwater
    harvesting system with rain sensors and water level detection.
    Implemented automated valve control to direct rainwater collection
    based on rainfall intensity and storage tank capacity.

-   **[Manvitha Reddy (2301CS29):]{.underline}** Developed the smart
    lighting system using ultrasonic sensors for motion detection.
    Created energy-efficient lighting control with automatic timeout
    features for testing and operation.

**Each subsystem functions independently while being integrated into a
cohesive smart home automation solution. The code demonstrates effective
teamwork through standardized timing mechanisms, shared hardware
resources, and consistent debugging outputs.**
