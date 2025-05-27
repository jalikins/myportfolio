---
title: "clemson_internship.txt" 
date: 2024-10-01 
draft: false
---
Between my junior and senior year of high school, I interned at Clemson University's International Center for Automotive Research (ICAR) in their robotics lab. I worked on a team of college students to create a robot that used machine learning to complete that year's [VEX Robotics Competition challenge](https://www.vexrobotics.com/competition?srsltid=AfmBOopaRRBhTduATjxg90Smleq9xV1jfcVkNqG2RwVNgNpbg2HHuEAf).

## Project Overview

The goal of the project was to create a robot that could autonomously navigate a field and complete tasks such as picking up and placing objects, while also avoiding obstacles. We also wanted to create a VEX AI team for Clemson University to compete in.

## Introduction

In VEX AI teams use the standard vex parts to build their robots but add an Intel D435, VEX GPS sensor, and use a Jetson Nano to tie them all together. With these parts, the robot can become completely autonomous.

In this year’s game, the team’s goal is to pick up one of the green tri-balls and put them under the net.

<div align="center">
    Vex Game Field
    <img src="/images/clemson/real_field.png" alt="Vex field" width="600" height="350">
</div>

## Stages of Development

First, **I created a virtual model of the robot using Onshape**, a CAD platform. This involved designing the robot's chassis, drivetrain, and the intake mechanism for picking up and placing the tri-balls. The goal was to create a design that could efficiently navigate the field and manipulate the game objects.

<div align="center">
    CAD Model of the Frame
    <img src="/images/clemson/cad_image.png" alt="CAD image" width="600" height="350">
</div>

The next step was using ISAAC Sim, NVIDIA's robotics simulator. **I contributed to creating a virtual environment** that mirrored the real-world VEX field. This allowed us to test the robot's design and the initial control algorithms in a simulated setting. Simultaneously, the team worked on the physical robot, integrating custom-designed and 3D-printed parts.

<div align="center">
    TIG Welding
    <img src="/images/clemson/weld.png" alt="TIG Welding" width="600" height="350">
</div>

The robot was equipped with a Jetson Nano GPU for real-time processing and an Intel Realsense camera, which provides 3D vision. To enable autonomous object recognition, **we implemented the YOLO object detection algorithm to identify the green tri-balls**. Additionally, the robot used odometry to estimate its position on the field.

<div align="center">
    Fully Assembled Robot
    <img src="/images/clemson/final_image.png" alt="Final version of physical robot" width="600" height="350">
</div>

Integrating the robot model and the environment in ISAAC Sim allowed us to begin testing the autonomous capabilities. We encountered challenges, such as accurately modeling the physical properties of the intake mechanism. For example, the initial model didn't account for the flexibility needed to grasp the tri-ball. **I helped resolve this by adjusting the physics properties of the intake in the simulator.**

<div align="center">
    Robot in ISAAC Sim
    <img src="/images/clemson/field_isaacsim.png" alt="Robot in ISAAC Sim" width="600" height="350">
</div>

<br>
<div align="center">
    Snapshot of A Star Pathfinding being implemented in ISAAC Sim
    <img src="/images/clemson/a_star.png" alt="Robot in ISAAC Sim with path" width="600" height="350">
</div>

To enable autonomous navigation, **we implemented A\* pathfinding**, an algorithm to find the shortest path between two points. The robot used the detected location of the tri-ball (from YOLO) and its own estimated position (from odometry) to plan a path to pick it up. The goal was for the robot to autonomously locate, pick up, and place the tri-ball under the net.

## Results

When driven with a remote, the robot could perform all the tasks it needed to. The robot was able to localize itself on the field and move to a point accurately. It was also able to spot the tri-ball's on the field.

## Future Work

The next step would be to improve environment that was built in the simulator to better mimic the real world. That way the machine learning algorithms can be trained in more realistic conditions allowing for better performance in the real world. 

## Conclusion

This project was a great learning experience for me, I was able to get early exposure to robotics and machine learning. I learned how to split up work on a big project like this. I also learned how to present my work to others in a clear and quick way because each week our professor overseeing the project would ask us to present what we accomplished that week.

## Links

[Link to My Poster On My LinkedIn](https://www.linkedin.com/in/jacoblikins/details/experience/1741444587209/single-media-viewer/?profileId=ACoAAD3HoCwBEsNSz1fnCk5PjqQ47ErkbKeOlWk)
