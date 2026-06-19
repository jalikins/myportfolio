---
title: "Autonomous Robotic Simulation"
description: "Modeled autonomous systems and evaluated intelligent control environments utilizing pathfinding algorithms in NVIDIA Isaac Sim."
pubDate: "August 2023"
heroImage: "/clemson/final_image.png"
badge: "Research"
---

## Overview
During my internship at Clemson University's International Center for Automotive Research (ICAR), I worked under a PHD candidate to create an autonomous robot for the VEX AI Competition. The goal was to have a system capable of autonomously navigating a  field, identifying targets (green tri-balls), and manipulating them while avoiding obstacles.

## The Tech Stack
* **Hardware:** Jetson Nano GPU, Intel RealSense D435 Camera, VEX GPS, Custom 3D Printed Parts
* **Software:** NVIDIA Isaac Sim, Onshape (CAD), YOLO (Machine Learning), Python, C
* **Skills:** TIG Welding, A* Pathfinding, Kinematic Simulation, Computer Vision

---

## The Engineering Process

### 1. Mechanical Design & Prototyping
I began by creating a complete virtual model of the robot using Onshape. This involved designing the chassis, drivetrain, and a specialized intake mechanism for object manipulation. Simultaneously, I assisted with the physical fabrication of the robot, which included integrating 3D-printed components and performing TIG welding on the frame.

![CAD of Robot](/clemson/cad_image.png)
*Caption: CAD design of robot*

![TIG Welding the Frame](/clemson/weld.png)
*Caption: fabrication and TIG welding of the robot chassis.*

### 2. Virtual Simulation in NVIDIA Isaac Sim
We needed a testing environment so, I contributed to building a virtual environment in NVIDIA Isaac Sim that mirrored the real-world competition field. 

For the physical robot, we used rubber bands to have high friction and flexability for picking up the tri-balls. A challenge was modeling this and I fixed this by adjusting the physics properties and friction coefficients of the intake components within the simulator to achieve realistic grasping behavior.

![Robot in ISAAC Sim](/clemson/field_isaacsim.png)
*Caption: The simulated testing environment built within NVIDIA Isaac Sim.*

### 3. Computer Vision & Autonomous Pathfinding
To make the robot autonomous, we added an Intel RealSense 3D camera and a Jetson Nano. We implemented the YOLO object detection algorithm to identify the game pieces, while utilizing odometry data to estimate our position on the field. 

To bridge the gap between "seeing" the object and "moving" to it, we used the A* pathfinding algorithm. The control logic used the YOLO detection coordinates and the robot's localized position to generate the shortest, obstacle-free path to the target.

![A Star Pathfinding](/clemson/a_star.png)
*Caption: Visualizing the A* pathfinding algorithm generating a route within the Isaac Sim environment as represented with red cubes.*

---

## Outcomes & Lessons Learned
The project successfully resulted in a functional prototype. Under remote operation, the robot could localized itself, recognize targets using it's camera, and navigate the environment. 

A key takeaway from this was the challenge of the sim-to-real gap. Future iterations of this project would require improving the simulator's environmental fidelity to allow machine learning algorithms to train in more realistic conditions before physical deployment. Beyond the technical skills, this internship provided experience in dividing work across a project and presenting weekly engineering updates to our overseeing professor.

## Complete Image Gallery

![Fully Assembled Robot](/clemson/final_image.png)
*Caption: The fully assembled physical robot equipped with the Jetson Nano and Intel RealSense camera.*

![Vex Game Field](/clemson/real_field.png)
*Caption: The physical competition field the robot was designed to navigate.*