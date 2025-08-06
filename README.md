# ir-maze-solver
An autonomous robot that solves mazes using four infrared (IR) sensor pairs. It detects walls by measuring reflected IR light from sensors on its front, left, and right sides. A microcontroller uses this data to implement a wall-following algorithm, enabling precise navigation around corners to find the exit.
IR Sensor Maze Solver Robot 🤖🧭
This document provides a complete guide for building and programming an autonomous maze-solving robot using the provided controller board. This project uses a four-IR-sensor array for precise wall detection and navigation, offering better performance than simpler setups.

Note: The labels on the PCB (GRBL, Spindle, etc.) are for its original CNC application. For this project, we will use these pins as general-purpose inputs/outputs for our sensors and motors.

## Key Features ✨
Autonomous Navigation: Solves simple mazes without human intervention.

Precise Sensing: A four-sensor IR array (left, front-left, front-right, right) allows for better wall-following, corner detection, and centering within corridors.

Arduino Core: Uses an Arduino Nano as the central processing unit.

Integrated Motor Driver: The onboard TB6612FNG chip efficiently drives two DC motors for a differential drive system.

All-in-One Board: Simplifies wiring by integrating power regulation, motor control, and I/O headers on a single PCB.

## Hardware & Connections 🔌
Component	Connected To	Description
Arduino Nano	Central Header	The brain of the robot.
Battery Pack	JP1 (+B, GND)	Main power source (e.g., 7.4V - 9V).
Left Motor	JP4 (or JP2)	Drives the left wheel.
Right Motor	JP2 (or JP4)	Drives the right wheel.
Left IR Sensor	JP5 (Z-Limit pin)	Senses walls on the immediate left.
Front-Left IR Sensor	JP5 (Y-Limit pin)	Senses walls on the front-left.
Front-Right IR Sensor	JP5 (X-Limit pin)	Senses walls on the front-right.
Right IR Sensor	JP6 (Probe pin)	Senses walls on the immediate right.

Export to Sheets
Sensor Power: All IR sensors require VCC and GND. You can get a stable 5V and GND from the multiple header pins available on the board.

## Calibration is Crucial!
Before running the code, you must calibrate your IR sensors. Each IR sensor module has a small potentiometer. Use a small screwdriver to turn it, adjusting the detection distance. Set it so the sensor's LED reliably turns ON when it's about 5-10 cm from a maze wall and OFF when it's further away.
