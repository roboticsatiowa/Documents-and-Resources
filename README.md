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
- [Acronyms and Terminology](#acronyms-and-terminology)
- [Helpful Resources](#helpfull-resources)
- [Authors](#authors)

## Full Block Diagram
<img src="https://raw.githubusercontent.com/roboticsatiowa/Documents-and-Resources/main/Diagrams/RoverFullBlockDiagram.svg">


<!-- codebase -->
## Codebase

##### [Embedded](https://github.com/roboticsatiowa/Rover_Embedded)
This repository contains the code that runs on the Teensy 4.1 microcontroller. It interfaces with the motor controllers and sensors on the rover. It is written in C/C++ and can be programmed with the PlatformIO extension for Visual Studio Code. Functionally, it acts as a bridge between the Raspberry Pi and the hardware by providing expanded I/O
<br>

##### [Base Station](https://github.com/roboticsatiowa/Base-Station)
This repository contains code that will run locally on the base station (at the time of writing my laptop). It uses a robotics framework called ROS2 (Robot Operating System 2). It consists of several simple nodes that handle various tasks such as parsing controller input, displaying sensor data, and sending commands to the rover. Most of the code is written in Python.
<br>

##### [Rover](https://github.com/roboticsatiowa/Rover)
The bulk of our code resides in this repository. It is a docker application which allows it to run on almost any hardware with docker suport. It is written in Python and uses the ROS2 framework. The code is responsible for everything involving control of the rover in addition to communication with the base station. It controls the rover by interfacing with the Teensy 4.1 over USB serial with a custom protocol.

## Datasheets

#### DM542T Stepper Motor Driver
<div>
  Datasheet: <a href=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Datasheets/DM542T.pdf>Local</a> - <a href=https://www.omc-stepperonline.com/download/DM542T.pdf>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/DM542T.png?raw=true><br>
</div>

Receives input from a microcontroller and high voltage from a power supply to drive a stepper motor. It takes 6 data pins: PUL+, PUL-, DIR+, DIR-, ENA+, and ENA-. Of these 6 data pins, 3 of them are grounds (PUL-, DIR- and ENA-). The ground pins can be ignored because their only purpose is to complete the electrical circuit so current can flow. ENA+ is left unconnected and can be ignored. This leaves 2 pins of importance: PUL+ and DIR+. DIR+ controls the direction of the stepper motor. When it is held high (3.3 volts or 5 volts) the motor will spin in one direction, then when its low (0 volts) it will spin in the opposite direction. PUL+ is a square wave that controls the speed of the motor. When there is no signal (0 volts) the motor will be stationary. When there is a square wave the motor will increment a small step each time the pin is pulsed. Rapid pulses will result in a high motor speed, while slow pulses will result in a slow motor speed.


#### Sabertooth 2x25 Motor Controller
<div>
  Datasheet: <a href=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Datasheets/Sabertooth2x25.pdf>Local</a> - <a href=TBD>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/Sabertooth.png?raw=true>
</div>

Dual motor controller with a variety of operating modes. It is capable of providing 25A to both of its DC outputs, hence its name. As of this writing, we use operation mode 3: simple serial (more info can be found in the datasheet). Each sabertooth recieves supply power via its B+ and B- pins. The M1A and M1B pins are attached to the first motor. M2A andn M2B pins attached to the second. Each motor's A and B outputs are reversable since DC motors can recieve both positive and negative voltages depending on the direction of rotation. The S1 pin is attached to the Tx (serial transmit) pin of whatever device is controlling the sabertooth. The S2 pin acts a motor select in case multiple sabertooth controllers want to share the same serial bus. In our case we leave it disconnected since every motor gets its own serial port.


#### Raspberry Pi 4 Model B

<div>
  Documentation: <a href=https://www.raspberrypi.com/documentation/computers/>External</a><br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/RaspberryPi4.png?raw=true><br>
</div>

Raspberry pi is a brand of SoC (system on a chip) commonly used by hobbiests for its cheap price and ease of use. SoC's are entire functioning computers which fit on a single circuit board. Nearly anything a desktop can do a raspberry pi can do as well (much more slowely). You can even play full 3D games like minecraft by attaching a monitor and keyboard. By having such a powerful computer onboard we are able to leverage existing software to perform most of the onboard tasks. Things such as networking, video compression, I/O, and more can be done easily by software bundled with its operating system. A simpler device running baremetal software would require decades of development to achieve the same. 


#### Teensy 4.1
<div>
  Documentation: <a href=https://www.pjrc.com/store/teensy41.html>External</a> (scroll for datasheets)<br>
  <img height=150px src=https://github.com/roboticsatiowa/Documents-and-Resources/blob/main/Media/Teensy41.png?raw=true><br>
</div>

Teensy is a line of microcontrollers known for its superior compute performance and I/O. It has no operating system which means it runs one program at a time directly on baremetal. With no OS all functionality must be written by hand or directly referenced as a library. They are extremely reliable if used correctly. No OS means no unnecesary faliure points from background software. We use our teensy to communcate with various motor drivers, encoders, sensors, and then give that info to the raspberry pi. The pi could not be used directly for these tasks because it lacks the proper I/O capabilities.


#### Battery
<div>
  Store Page: <a href=https://zeeebattery.com/products/zeee-6s-lipo-battery-22-2v-100c-6000mah-ec5>External</a><br>
  <img height=150px src="https://zeeebattery.com/cdn/shop/files/1-1_e826b90e-5d53-44cd-8a35-02282e267e40_597x597.jpg?v=1710928065=true"><br>
    <b>BATTERIES ARE EXTREMELY DANGEROUS. FIND AN EXPERIENCED MEMBER TO HELP</b><br>
</div>
    This is a 6000 mah 6S LiPo battery. This means that it contains 6 lithium polymer (LiPo) cells in series and has a total capacity of 6000 milliamp-hours (1 amp-hour per cell). a LiPo battery has a minimum and maximum voltage of 3.2 and 4.2 volts respectivly. This means there is a total range of 19.2 to 25.2 volts. If the battery is overcharged or over discharged outside this range it will degrade in performance rapidly and immediately. Use extreme caution not to overcharge or overdischarge the batteries. 

## Acronyms and Terminology

| Word/Acronym | Acronym Definition                  | Description                                                                                          | Additional links/information |
| :----------- | :---------------------------------- | :--------------------------------------------------------------------------------------------------- | :--------------------------- |
| PWM          | Pulse Width Modulation              | A voltage square wave of varying frequency and duty cycle                                            |                              |
| Duty Cycle   | N/A                                 | The ratio of high time to low time in a square wave given as a percentage                            |                              |
| Serial       | N/A                                 | A type of communication between computers where data is sent 1 bit at a time                         |                              |
| Kernal       | N/A                                 | Software that bridges between computer hardware and software. manages memory, threads, etc.          |                              |
| Linux        | N/A                                 | An operating system kernal often used because of its customizability and reliability                 |                              |
| Linux Distro | Linux Distribution                  | Different versions of linux which all use the same kernal but different customization out of the box |                              |


## Helpful Resources

- ROS2
  - [Documentation](https://docs.ros.org/en/humble/index.html)
  - [What is ROS2? (YouTube)](https://www.youtube.com/watch?v=7TVWlADXwRw)
  - [Articulate Robotics (YouTube)](https://www.youtube.com/@ArticulatedRobotics)
- Docker
  - [Website](https://www.docker.com/)
  - [Docker in 100 Seconds (YouTube)](https://www.youtube.com/watch?v=Gjnup-PuquQ)
  - [Learn Docker in 7 Easy Steps (YouTube)](https://www.youtube.com/watch?v=gAkwW2tuIqE)
- Raspberry Pi
  - [Website](https://www.raspberrypi.org/)
  - [Raspberry Pi in 100 Seconds (YouTube)](https://www.youtube.com/watch?v=eZ74x6dVYes)
- Foxglove Studio
  - [Website](https://foxglove.dev/)
- Zenoh middleware
  - [](https://zenoh.io/blog/2021-09-28-iac-experiences-from-the-trenches/)
## ✍️ Authors <a name = "authors"></a>

- [@ethanholter](https://github.com/ethanholter) - Responsible for this mess :\)
