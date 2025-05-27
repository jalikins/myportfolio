---
title: "remote_controlled_golf_cart.txt"
date: 2024-10-01
draft: false
customcss: "/css/custom.css" 
---

I contributed to a golf cart project that could be **controlled remotely using an Xbox controller**. This project was undertaken during my time as a high school student at the [South Carolina Governor's School for Science and Mathematics](https://www.scgssm.org/) (GSSM). As the project was initiated before my involvement, I **integrated with the existing work** of previous students.

<div align="center"> <img src="/images/golfcart/full_golfcart.jpg" alt="Full view of the remote controlled golf cart" width="400" height="350">
</div>

## What We Inherited

Previous students had already made significant progress, having **acquired a golf cart** and **integrated actuators for electronic control of the steering column and brake pedal**. They had also planned a main control box to centralize the wiring. Facing limited documentation, we **reverse-engineered the existing wiring** using the golf cart's wiring diagram and a multimeter.

<div align="center"> <img src="/images/golfcart/mother_box.jpg" alt="Main control box for golf cart electronics" width="300" height="250">
</div>

## What We Had to Learn

At the project's outset, my electronics knowledge was limited. Through **self-directed learning involving research and experimentation**, I gained an understanding of the golf cart's wiring and the interaction of its components. This learning was documented in a shared notebook.

[Link to the learning notebook](https://docs.google.com/document/d/1cRf5sPQzyxRte2nKm2wTEJMhRPuGPrmT7tP-VwHH7v0/edit?usp=sharing)

## What Was Done

We utilized an **Arduino as the microcontroller** for the project. My contributions included **programming the Arduino to interface with motor shields** that controlled the steering and brake actuators. I also **implemented a digital potentiometer** controlled by the Arduino to replicate the analog signal for the accelerator pedal. Additionally, the Arduino **controlled a relay to manage the forward and reverse solenoids**.

Below is the rough schematic of the wiring of the arduino to the different components of the golf cart.

<div align="center"> <img src="/images/golfcart/schematic.jpeg" alt="Wiring schematic for Arduino and golf cart components" width="400" height="350">
</div>

## What We Accomplished

We successfully achieved **remote control of the golf cart's forward and backward movement**. While we encountered a limitation with the initial motor shield for steering, which proved underpowered, we did identify a working alternative. However, time constraints prevented its full integration before the end of the school year.

## Future Work

The next planned phase involves **designing a custom PCB** to consolidate the control electronics. The long-term vision is to develop a **fully autonomous golf cart** using lidar and cameras for navigation. Our work laid the groundwork for this future autonomy.

## Pictures

<div align="center">
    Front view of golf cart with steering actuator and brake actuator installed.
    Steering actuator is connected to left side of wheel and brake actuator is on the right side lidar.
    <br> <img src="/images/golfcart/front_golf.jpeg" alt="Front view of golf cart with actuators" width="400" height="350">
    </div>

<br>
<div align="center">
    Below is close up of arduino, digital potentiometer, and motor shields.
    <br> <img src="/images/golfcart/board.jpeg" alt="Close up of Arduino, potentiometer, and motor shields" width="400" height="350">
</div>

<br>
<div align="center">
    These are the solenoids that control the forward and reverse of the golf cart. The solenoids are connected to the relay that is controlled by the Arduino. The right solenoid is initialized then either the forward or reverse solenoid is activated to move the golf cart in the desired direction.
    <br> <img src="/images/golfcart/solinoids.jpg" alt="Solenoids for golf cart forward and reverse control" width="400" height="350">
</div>