---
title: "Remote Controlled Golf Cart"
description: "Engineered control electronics and mapped power distribution to convert a standard golf cart into a remote-operated vehicle."
pubDate: "October 2024"
heroImage: "/golfcart/full_golfcart.jpg"
badge: "Hardware Integration"
---

## Overview
I contributed to a project converting a standard golf cart into a vehicle that could be controlled remotely using an Xbox controller. This was undertaken during my time at the South Carolina Governor's School for Science and Mathematics (GSSM). Since the project was initiated before my involvement, my primary objective was to reverse-engineer existing systems and integrate the central electronic control logic.

## My Role & The Tech Stack
* **Role:** Electronics Integration & System Mapping
* **Hardware:** Arduino, Motor Shields, Digital Potentiometers, Actuators, High-Current Solenoids
* **Skills:** Reverse Engineering, Electromechanical Integration, Multimeter Diagnostics

---

## The Engineering Process

### 1. Reverse Engineering Inherited Systems
Previous students had made significant mechanical progress by mounting actuators for electronic control of the steering column and brake pedal. However, we faced limited documentation on the electronics. To move forward, we had to reverse-engineer the existing wiring using the golf cart's original wiring diagrams and extensive multimeter testing.

### 2. Control Electronics & The "Mother Box"
To centralize the wiring, we built a main control unit. I engaged in heavy self-directed learning to understand the cart's native high-voltage power distribution. We utilized an Arduino paired with digital potentiometers and motor shields to translate the Xbox controller inputs into physical mechanical actions. 

![Main control box for golf cart electronics](/golfcart/mother_box.jpg)
*Caption: The main "Mother Box" centralizing the control electronics.*

### 3. Drive Control & High-Current Switching
One of the major challenges was safely controlling the forward and reverse motion of the heavy vehicle. We integrated large solenoids connected to relays that were controlled by the Arduino. The system initializes the right solenoid, and then activates either the forward or reverse solenoid to safely switch the high-current drive lines based on the controller input.

![Solenoids for golf cart forward and reverse control](/golfcart/solinoids.jpg)
*Caption: High-current solenoids used to physically switch the drive direction of the vehicle.*

---

## Outcomes & Future Work
While some of the mechanical actuators proved slightly underpowered for the vehicle's weight, we successfully mapped the control logic and proved the viability of the remote-control interface. Time constraints prevented full integration before graduation, but our work laid a complete foundation for the next phase.

The long-term vision for this platform is to design a custom PCB to consolidate the Arduino and motor shields, ultimately allowing future students to develop a fully autonomous platform using lidar and cameras.

## Complete Image Gallery

![Front view of golf cart with actuators](/golfcart/front_golf.jpeg)
*Caption: Front view showing the steering actuator connected to the left side of the wheel mechanism, and the brake actuator (with LiDAR mount) on the right.*

![Close up of Arduino, potentiometer, and motor shields](/golfcart/board.jpeg)
*Caption: A close-up of the Arduino logic board, digital potentiometers, and motor shields prior to final box integration.*