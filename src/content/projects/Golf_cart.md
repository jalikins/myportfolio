---
title: "Remote Controlled Golf Cart"
description: "Engineered control electronics and mapped power distribution to convert a standard golf cart into a remote-operated vehicle."
pubDate: "October 2024"
heroImage: "/golfcart/full_golfcart.jpg"
badge: "Hardware Integration"
---

## Overview
I contributed to a project converting a standard golf cart into a vehicle that could be controlled remotely using an Xbox controller. This was during my time at the South Carolina Governor's School for Science and Mathematics (GSSM). Since the project was started before my involvement, my main goal was to learn existing systems and integrate the central electronic control logic.

## My Role & The Tech Stack
* **Role:** Electronics Integration & System Mapping
* **Hardware:** Arduino, Motor Shields, Digital Potentiometers, Actuators, High-Current Solenoids
* **Skills:** Reverse Engineering, Electromechanical Integration, Multimeter Diagnostics

---

## The Engineering Process

### 1. Reverse Engineering Inherited Systems
Previous students made significant mechanical progress by welding actuators for electronic control of the steering column and brake pedal. However, there was not much to go off on for the control system. Moving forward, we reverse-engineered the existing wiring using multimeter testing.

### 2. Control Electronics & The "Mother Box"
We built a main control unit that was the heart of the Golf Cart. We used an Arduino paired with digital potentiometers and motor shields to translate the Xbox controller inputs into physical mechanical actions. 

![Main control box for golf cart electronics](/golfcart/mother_box.jpg)
*Caption: The main "Mother Box" centralizing the control electronics.*


![Solenoids for golf cart forward and reverse control](/golfcart/solinoids.jpg)
*Caption: High-current solenoids used to physically switch the drive direction of the vehicle.*

---

## Outcomes & Future Work
The long-term vision for this platform is to design a custom PCB to consolidate the Arduino and motor shields, ultimately allowing future students to develop a fully autonomous platform using lidar and cameras.

## Complete Image Gallery

![Front view of golf cart with actuators](/golfcart/front_golf.jpeg)
*Caption: Front view showing the steering actuator connected to the left side of the wheel mechanism, and the brake actuator (with LiDAR mount) on the right.*

![Close up of Arduino, potentiometer, and motor shields](/golfcart/board.jpeg)
*Caption: A close-up of the Arduino logic board, digital potentiometers, and motor shields prior to final box integration.*