# Version 4 of my Robotics Arm project
---
## General
This project is my fourth attempt at building a robotics arm.
---
## Goal
Get a robotics arm to recognize a Rubics Cube, manipulate, and solve it.
---
## Layout
**Raspberry pi 3+** is the main computer and its responsibilities are:
* OpenCV - get and process camera and stero image
* TensorFlow - run a Neural Network with the data to find the Rubics Cube
* ROS - control the robotics arm position

**Arduino Mega** handles the middleware between ROS and motors
* Take the data instruction from ROS and send instructions to move the arm
* Query the positioning of the motors and send it back to the raspberry
* Determine if the robotics runs into something in the environment

**Arduino Nanos** each are responsible for one motor, pressure sensor, and 
* Receive instructions from Mega and move the motor to specific position
* Send the current position of the motor for the Mega
* Query the sensor to see if the motor has hit a "wall" and report back any issues
---
![Image](https://github.com/aalhag24/RoboticArmAI/Img/Outline.png)
