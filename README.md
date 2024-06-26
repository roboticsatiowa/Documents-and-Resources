<div align="center">
  <a href="" rel="noopener">
 <img height=200px src="https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/Banner.png?raw=true" alt="Project logo"></a>
</div>

<h2 align="center"> Robotics at Iowa - Documentation and Resources </h3>

---

## 📝 Table of Contents
- [Codebase](#codebase)
  - [Embedded](#embedded)
  - [Base Station](#base-station)
  - [Rover](#rover)
- [Datasheets](#datasheets)
  - [DM542T Stepper Motor Driver](#dm542t-stepper-motor-driver)
  - [Sabertooth 2x25 Motor Controller](#sabertooth-2x25-motor-controller)
  - [Raspberry Pi 4 Model B](#raspberry-pi-4-model-b)
  - [Teensy 4.1](#teensy-41)
- [Helpful Resources](#helpfull-resources)
- [Authors](#authors)

<!-- codebase -->
## 🖥️ Codebase

##### [Embedded](https://github.com/roboticsatiowa/Rover_Embedded)
This repository contains the code that runs on the Teensy 4.1 microcontroller. It interfaces with the motor controllers and sensors on the rover. It is written in C/C++ and can be programmed with the PlatformIO extension for Visual Studio Code. Functionally, it acts as a bridge between the Raspberry Pi and the hardware by providing expanded I/O
<br>

##### [Base Station](https://github.com/roboticsatiowa/Base-Station)
This repository contains code that will run locally on the base station (at the time of writing my laptop). It uses a robotics framework called ROS2 (Robot Operating System 2). It consists of several simple nodes that handle various tasks such as parsing controller input, displaying sensor data, and sending commands to the rover. Most of the code is written in Python.
<br>

##### [Rover](https://github.com/roboticsatiowa/Rover)
The bulk of our code resides in this repository. It is a docker application which allows it to run on almost any hardware with docker suport. It is written in Python and uses the ROS2 framework. The code is responsible for everything involving control of the rover in addition to communication with the base station. It controls the rover by interfacing with the Teensy 4.1 over USB serial with a custom protocol.

## 📁 Datasheets

<!-- https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/DM542T.png?raw=true -->

<div> 
  <b>DM542T Stepper Motor Driver</b><br>
  Datasheet: <a href=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Datasheets/DM542T.pdf>Local</a> - <a href=https://www.omc-stepperonline.com/download/DM542T.pdf>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/DM542T.png?raw=true><br>
  Receives input from a microcontroller and high voltage from a power supply to drive a stepper motor.
</div>
<br>
<br>
<div>
  <b>Sabertooth 2x25 Motor Controller</b><br>
  Datasheet: <a href=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Datasheets/Sabertooth2x25.pdf>Local</a> - <a href=TBD>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/Sabertooth.png?raw=true><br>
  Dual motor controller that can be be controlled via serial. Outputs 25A to 2 motors, hence the name 2x25.
</div>
<br>
<br>
<div>
  <b>Raspberry Pi 4 Model B</b><br>
  Documentation: <a href=https://www.raspberrypi.com/documentation/computers/>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/RaspberryPi4.png?raw=true><br>
  Miniature computer often runnning Linux that can be used for a variety of applications.. We use it as our main onboard computer.
</div>
<br>
<br>
<!-- Teensy 4.1 -->
<div>
  <b>Teensy 4.1</b><br>
  Documentation: <a href=https://www.pjrc.com/store/teensy41.html>External</a> (scroll for datasheets)<br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/Teensy41.png?raw=true><br>
  Microcontroller that can be programmed with the Arduino IDE. It lacks the processing power of the Raspberry Pi and has no operating system, but has more I/O. We use it to interface with sensors and motor controllers.

## Helpful Resources

- ROS2
  - [Documentation](https://docs.ros.org/en/humble/index.html)
  - [What is ROS2? (YouTube)](https://www.youtube.com/watch?v=7TVWlADXwRw)
  - [Articulate Robotics (YouTube)](https://www.youtube.com/@ArticulatedRobotics)
- Docker
  - [Website](https://www.docker.com/)
  - [Docker in 100 Seconds (YouTube)](https://www.youtube.com/watch?v=Gjnup-PuquQ)
- Raspberry Pi
  - [Website](https://www.raspberrypi.org/)
  - [Raspberry Pi in 100 Seconds (YouTube)](https://www.youtube.com/watch?v=eZ74x6dVYes)
- Foxglove Studio
  - [Website](https://foxglove.dev/)
## ✍️ Authors <a name = "authors"></a>

- [@ethanholter](https://github.com/ethanholter) - Responsible for this mess :\)
