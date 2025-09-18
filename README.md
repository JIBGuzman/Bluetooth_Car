# Bluetooth Car

## Overview
Bluetooth Car is a robot car controlled via Bluetooth using a TM4C123 microcontroller and an HC-05 Bluetooth module. The car can be operated in two modes: autonomous pre-programmed movement patterns and real-time manual control via Bluetooth serial terminal commands.

## Features
- **Mode 1 (Demo Mode):** Executes predefined movement patterns such as figure eight, circle, square, and zigzag upon receiving specific commands.
- **Mode 2 (Free Driving Mode):** Manual control of the car's movements with commands to move forward, backward, turn left/right, stop, and adjust speed.
- LED indicators display the current mode (green for Mode 1, blue for Mode 2).
- Onboard switch toggles between modes with interrupt handling for smooth switching.

## Hardware Components
- TM4C123 LaunchPad microcontroller
- HC-05 Bluetooth module
- Romi Car chassis with DC motors
- Jumper wires
- Onboard LEDs and switch on the LaunchPad

### Key Connections
- UART communication using Port B pins 0 and 1 (TX/RX) between TM4C123 and HC-05
- Motor control direction on Port E pins 0–3
- PWM speed control on Port B pins 6 and 7
- Mode switch on Port F pin 4
- Mode LEDs on Port F pins 1–3

## Software Design
- UART configured for Bluetooth data transmission
- PWM for precise DC motor speed control
- GPIO for motor direction control
- Interrupts to handle mode switching
- Main loop processes Bluetooth commands depending on the current mode

## Usage Instructions
1. Power the TM4C123 LaunchPad and connect the HC-05 Bluetooth module.
2. Pair your device with HC-05 via Bluetooth serial terminal app.
3. Use the onboard switch to toggle between modes.
4. In **Mode 1 (Demo Mode)**, send:
   - `8` to perform figure eight,
   - `C` for circle,
   - `S` for square,
   - `Z` for zigzag pattern.
5. In **Mode 2 (Free Driving Mode)**, send:
   - `F` to move forward,
   - `B` to move backward,
   - `L` to turn left,
   - `R` to turn right,
   - `S` to stop,
   - `U` to speed up,
   - `D` to slow down.
6. Observe the mode LED color for confirmation.

## Challenges and Learnings
- Configuring HC-05 for UART communication and correct baud rate
- Fine-tuning PWM signals for smooth motor control
- Minimizing latency between command reception and motor execution
- Implementing reliable interrupt-driven mode switching

## Contributors
- Jonathan Cerniaz
- Afzal Hakim
- Joseph Guzman
- Robby Rimal

## Additional Resources
- Video Demo Mode 1: [https://youtu.be/xGGCauwmHAY]
- Video Demo Mode 2: [https://youtu.be/T0b7mr1MAmc]
