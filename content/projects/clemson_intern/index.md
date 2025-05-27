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

First, I created a virtual model of the robot using Onshape, a CAD platform. I designed the robot to be able to navigate the field and complete the tasks. This involved designing the robot's chassis, drivetrain, and choosing how it would pick up and place objects.

<div align="center">
    CAD Model of the Frame
    <img src="/images/clemson/cad_image.png" alt="CAD image" width="600" height="350">
</div>

The next step is using ISAAC Sim, NVIDIA's robotics simulator, this involved creating a virtual environment that mimics the real-world field and testing the robot's design in that environment. While creating the environment, we made the physical robot and put our own custom parts on it.

<div align="center">
    TIG Welding
    <img src="/images/clemson/weld.png" alt="TIG Welding" width="600" height="350">
</div>
 
 The robot was deployed using the Jetson Nano GPU, for real-time computing, and the Intel Realsense camera, which uses an infrared sensor and two cameras to see in three dimensions. The robot also uses the YOLO object detection algorithm to recognize game elements. Additionally, with odometry, the robot can localize its position within the field.

<div align="center">
    Fully Assembled Robot
    <img src="/images/clemson/final_image.png" alt="Final version of physical robot" width="600" height="350">
</div>

Then the robot and the environment were put together in ISAAC Sim to begin testing how the robot would perform. There were many issues that came up, mostly due to incorrectly dealing with the physics of the robot. An example of this is in order to pick up the tri-ball, the intake would need to behave like a rubber band and stretch but the model would not allow that. This was fixed by changing the physics of the intake to allow it to stretch and compress.

<div align="center">
    Robot in ISAAC Sim
    <img src="/images/clemson/field_isaacsim.png" alt="Robot in ISAAC Sim" width="600" height="350">
</div>

<br>
<div align="center">
    Snapshot of A Star Pathfinding being implemented in ISAAC Sim
    <img src="/images/clemson/a_star.png" alt="Robot in ISAAC Sim with path" width="600" height="350">
</div>

The robot needed to find the best path to the tri-ball and then pick it up. This was done by using the YOLO object detection algorithm to spot the tri-ball and using odometry to localize the robot's position on the field then using A* pathfinding to find the best path to the tri-ball. The robot would then use its intake to pick up the tri-ball and place it under the net.

## Results

When driven with a remote, the robot could perform all the tasks it needed to. The robot was able to localize itself on the field and move to a point accurately. It was also able to spot the tri-ball's on the field.

## Future Work

The next step would be to improve environment that was built in the simulator to better mimic the real world. That way the machine learning algorithms can be trained in more realistic conditions allowing for better performance in the real world. 

## Conclusion

This project was a great learning experience for me, I was able to get early exposure to robotics and machine learning. I learned how to split up work on a big project like this. I also learned how to present my work to others in a clear and quick way because each week our professor overseeing the project would ask us to present what we accomplished that week.

## Links

[Link to My Poster On My LinkedIn](https://www.linkedin.com/in/jacoblikins/details/experience/1741444587209/single-media-viewer/?profileId=ACoAAD3HoCwBEsNSz1fnCk5PjqQ47ErkbKeOlWk)
