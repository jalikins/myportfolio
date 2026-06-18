---
title: "Autonomous Robotic Simulation"
description: "Modeled autonomous systems and evaluated intelligent control environments utilizing pathfinding algorithms in NVIDIA Isaac Sim."
pubDate: "August 2023"
heroImage: "/clemson/cad_image.png"
badge: "Research"
---

## Overview
During an internship at Clemson University's International Center for Automotive Research (ICAR), I collaborated with a collegiate engineering team to develop a fully autonomous robot for the VEX AI Competition. The objective was to engineer a system capable of autonomously navigating a complex field, identifying specific targets (green tri-balls), and manipulating them while dynamically avoiding obstacles.

## My Role & The Tech Stack
* **Role:** Robotics Research Intern
* **Hardware:** Jetson Nano GPU, Intel RealSense D435 Camera, VEX GPS, Custom 3D Printed Parts
* **Software:** NVIDIA Isaac Sim, Onshape (CAD), YOLO (Machine Learning), Python
* **Skills:** TIG Welding, A* Pathfinding, Kinematic Simulation, Computer Vision

---

## The Engineering Process

### 1. Mechanical Design & Prototyping
I began by creating a complete virtual model of the robot using Onshape. This involved designing the chassis, drivetrain, and a specialized intake mechanism for object manipulation. Simultaneously, I assisted with the physical fabrication of the robot, which included integrating 3D-printed components and performing TIG welding on the frame.

![TIG Welding the Frame](/clemson/weld.png)
*Caption: Assisting with the physical fabrication and TIG welding of the robot chassis.*

### 2. Virtual Simulation in NVIDIA Isaac Sim
Before deploying code to the physical hardware, we needed a robust testing environment. I contributed to building a virtual environment in NVIDIA Isaac Sim that mirrored the real-world competition field. 

One major challenge was accurately modeling the physical flexibility of the intake mechanism required to grasp objects. I resolved this by manually adjusting the physics properties and friction coefficients of the intake components within the simulator to achieve realistic grasping behavior.

![Robot in ISAAC Sim](/clemson/field_isaacsim.png)
*Caption: The simulated testing environment built within NVIDIA Isaac Sim.*

### 3. Computer Vision & Autonomous Pathfinding
To make the robot autonomous, we integrated an Intel RealSense 3D camera and a Jetson Nano. We implemented the YOLO object detection algorithm to identify the game pieces, while utilizing odometry data to estimate our position on the field. 

To bridge the gap between "seeing" the object and "moving" to it, we implemented A* pathfinding. The control logic used the YOLO detection coordinates and the robot's localized position to generate the shortest, obstacle-free path to the target.

![A Star Pathfinding](/clemson/a_star.png)
*Caption: Visualizing the A* pathfinding algorithm generating a route within the Isaac Sim environment.*

---

## Outcomes & Lessons Learned
The project successfully resulted in a functional prototype. Under remote operation, the robot accurately localized itself, recognized targets using the computer vision model, and navigated the environment. 

A key takeaway from this research was the challenge of the "sim-to-real" gap. Future iterations of this project would require improving the simulator's environmental fidelity to allow machine learning algorithms to train in more realistic conditions before physical deployment. Beyond the technical skills, this internship provided invaluable experience in dividing work across a large project and presenting weekly engineering updates to our overseeing professor.

## Complete Image Gallery

![Fully Assembled Robot](/clemson/final_image.png)
*Caption: The fully assembled physical robot equipped with the Jetson Nano and Intel RealSense camera.*

![Vex Game Field](/clemson/real_field.png)
*Caption: The physical competition field the robot was designed to navigate.*