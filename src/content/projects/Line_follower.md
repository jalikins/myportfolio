---
title: "Autonomous Line Following Robot"
description: "Developed a closed-loop PID control system utilizing a 4-sensor IR array to enable high-speed autonomous navigation."
pubDate: "October 2024"
heroImage: "/post_img.webp"
badge: "Robotics"
---
This is still work in progress
## Overview
This project involved developing a two-wheeled autonomous robotic platform capable of navigating a complex track as quickly as possible. The engineering challenge was integrating real-time physical sensors with a closed-loop control algorithm to adjust the vehicle's trajectory at high speeds.

## My Role & The Tech Stack.
* **Hardware:** Arduino Uno, Adafruit Motor Shield V2, 4x TCRT5000 IR Reflectance Sensors, DC Gearmotors
* **Software:** C (Arduino), Serial Communication
* **Skills:** Closed-Loop Control (PID), Sensor Normalization, Embedded Systems Programming

---

## The Engineering Process

* **Team Division:** I led the software architecture and control systems (specifically the PID controller and sensor data pipeline), while my partner, Mira Epstein, led the mechanical assembly, chassis configuration, and custom PLA 3D-printed mounts

### 1. Sensor Array & Data Normalization
To keep the robot centered, we used an array of four TCRT5000 infrared reflectance sensors mounted to the front chassis. The raw analog readings from these sensors fluctuate based on ambient light and surface height, so I wrote a data pipeline to normalize the values (mapping raw 60-380 bounds to a standard 0-1000 range). 

Once normalized, I applied a weighted average algorithm. By assigning specific weights to each sensor (`[-3, -1, 1, 3]`), the software could calculate an `error` value representing exactly how far the center of the robot had drifted from the target line.

### 2. Closed-Loop PID Control
Instead of using a simple "bang-bang" (left/right) algorithm, I used a full Proportional-Integral-Derivative (PID) controller to increase the speed through the track.
* **Proportional (P):** Reacted to the immediate drift error.
* **Integral (I):** Accumulated past errors to correct for slight, continuous misalignments.
* **Derivative (D):** Calculated the rate of change of the error, allowing the robot to "predict" sharp turns and prevent overshooting.

The output of this PID equation was  applied to the base speed of the left and right DC motors, allowing the robot to smoothly accelerate through straightaways and brake into sharp turns.

### 3. Real-Time Serial Tuning Interface
One of the biggest hurdles in control systems is tuning the $K_p$, $K_i$, and $K_d$ multiplier variables. Recompiling and uploading Arduino code for every single micro-adjustment was incredibly inefficient. To solve this, I built a serial interface that allowed me to send new tuning parameters directly from my laptop to the Arduino while the robot was running. This enabled rapid iteration and allowed us to perfectly dial in the motor response on the fly.

---

## Outcomes
The integration of a normalized 4-sensor array with a finely tuned PID controller resulted in a highly responsive platform. The robot successfully maintained its trajectory through sharp sub-90-degree turns without losing the track. This project solidified my understanding of embedded systems, hardware-software integration, and control theory mathematics.

## Image Gallery
*(Add photos of the physical robot chassis, a close-up of the Arduino/Motor shield wiring, and a diagram of your PID loop here)*

![Physical Robot Assembly](/post_img.webp)
*Caption: The fully assembled robotic platform featuring the front-mounted IR sensor array and dual DC gearmotors.*