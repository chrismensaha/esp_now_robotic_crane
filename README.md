# ESP-NOW-Robotic-Crane
A low-latency, wireless robotic crane system built with two ESP32 microcontrollers.

## Overview
- The main goal of this project is to build a 3 Degree of Freedom robotic crane that is wirelessly controlled using the ESP-NOW. 
- The project focus is on embedded systems, real-time communication, and hardware-software integration.
  
## Goals
- Goal 1: Setup ESP-NOW communication.
- Goal 2: Single axis servo control.
- Goal 3: 3 degree of freedom movement and power management.
- Goal 4: Mechanical assembly and cable management.

## Specifications
- Hardware: Two ESP32s, 3 Servos, and a Joystick Module.
- Communication: ESP-NOW (Low-latency Peer-to-Peer).
- Environment: Arduino IDE

## System
The system consists of two independent nodes communicating over a connectionless 2.4GHz protocol:
1. The Remote/Transmitter:
   - Reads analog joystick values.
   - Packages data into a C-struct.
   - Broadcasts data via ESP-NOW to the specific MAC address of the Crane.

2. The Crane/Receiver:
   - Listens for incoming ESP-NOW packets.
   - Unpacks the data struct.
   - Maps values to PWM signals for the Servo motors.
   - Implements safety constraints
