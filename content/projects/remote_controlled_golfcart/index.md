---
title: "remote_controlled_golf_cart.txt"
date: 2024-10-01
draft: false
customcss: "/css/custom.css" # Ensure your head.html uses this, or link custom.css directly
---

I worked on a golf cart project that could be controlled remotely using a xbox controller. I did this project, while I was a high school student at [South Carolina Governor's School for Science and Mathematics](https://www.scgssm.org/) (GSSM). The project started before I started at GSSM, so I had to pick up where previous students left off.

<div align="center"> <img src="/images/golfcart/full_golfcart.jpg" alt="Full view of the remote controlled golf cart" width="400" height="350">
</div>

## What We Inherited

The previous students had made a lot of progress on the project, they had already acquired a golf cart and welded an actuator on the steering column to control the steering electronically as well as the brake pedal so everything could be controlled. They also planned a main control box that would connect the wiring throughout the golf cart in one central location. We were also given little documentation on how the previous students had wired the golf cart, so we figured out how to wire the golf cart by looking at the wiring diagram of the golf cart and using a multimeter to test the connections.

<div align="center"> <img src="/images/golfcart/mother_box.jpg" alt="Main control box for golf cart electronics" width="300" height="250">
</div>

## What We Had to Learn

Beginning of project, we knew very little about electronics, so we taught ourselves the wiring of the golf cart and how the different components worked together. We created a notebook to document our findings and useful information for controlling the golf cart.

[Link to the learning notebook](https://docs.google.com/document/d/1cRf5sPQzyxRte2nKm2wTEJMhRPuGPrmT7tP-VwHH7v0/edit?usp=sharing)

## What Was Done

We used an Arduino as the micro controller for the project. I used the Arduino to interact with the motor shields that controlled the steering and brake actuator. I also used the Arduino to work with a digital potentiometer chip to replicate the analog signal that the golf cart's accelerator pedal would normally send to the motor controller. The Arduino also communicated to a relay that would activate the solenoids and decide whether the golf cart was in forward or reverse.

Below is the rough schematic of the wiring of the arduino to the different components of the golf cart.

<div align="center"> <img src="/images/golfcart/schematic.jpeg" alt="Wiring schematic for Arduino and golf cart components" width="400" height="350">
</div>

## What We Accomplished

We were able to get the golf cart to move forward and backward, although we were not able to get the steering to work. The issue was the motor shield that we were using to control the steering was not powerful enough and would burn out when we tried to turn the steering. We were able to get the steering to work with a different motor shield, but we did not have enough time to implement it into the project before the end of the school year.

## Future Work

Creating a custom PCB board to control the golf cart would be the next step in the project. The end goal is to have a fully autonomous golf cart that uses lidar and cameras to navigate a course. The PCB board would allow us to take in the sensor data and control movement based on the data. We showed that we took the golf cart to the next step, but there is still a lot of work to be done to make it fully autonomous.

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