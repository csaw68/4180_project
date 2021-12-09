## The web page should explain the project idea, provide instructions, code, and hardware setups 
# Hand Gesture Controlled Robot through OpenCV and an IoT Webserver
ECE 4180 Final Project 

insert image of robot - look more legit

# Authors
Feng Yunchu, Faiza Yousuf, Harry Nguyen, Christine Saw

# Table of Contents
- [Overview](README.md#overview)
- [Parts List](README.md#parts-list)
- [Hardware Setups](README.md#hardware-setups)
  - [Vehicle Setup](README.md#vehicle-setup)
  - [Raspberry Pi 4](README.md#pin-connection-of-the-pi)
  - [mbed LPC1768](README.md#pin-connection-of-the-mbed)
- [Table of Commands](README.md#table-of-commands)
- [Instructions](README.md#instructions)
- [Demo Video](README.md#demo-video)
- [Future Improvements](README.md#future-improvements)

# Overview
This project aims to create a hand gesture-controlled car that can recognize hand commands to move and perform four motions. It uses a Pi camera to capture hand gestures, a Raspberry Pi 4 to interface with the Pi camera and translate detected hand gestures into commands that are sent to a server run by an MBED (using a ESP8266 module). Finally, the MBED takes the commands and moves the robot accordingly.

<img src="https://user-images.githubusercontent.com/78784280/145411276-7d4bd055-054c-4d5b-b3a5-7a5d652541ab.png" width="850">

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Parts List
- Hardware:
  - Raspberry Pi 4
  - mbed LPC1768
  - Pi Camera
  - 2 DC motors 
  - Dual H-bridge breakout board 
  - 4 LED lights (and 330 Ohm resistors)
  - Power supply with stable amp (4AA battery pack and power bank)
  - ESP8266 module

- Software:
  - Python 3
  - OpenCV
  - Thonny - compiler seen in demo
  - MBED online compiler

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Hardware Setups

## Vehicle Setup
Instructions on how to assemble the vehicle's base build can be found here: https://learn.sparkfun.com/tutorials/assembly-guide-for-redbot-with-shadow-chassis/all

## Pin connection of the Pi
<img src="https://user-images.githubusercontent.com/78784280/145406918-eed09443-98ee-4211-9d10-eaa107adf42a.PNG" width="500">

## Pin connection of the mbed
<img src="https://user-images.githubusercontent.com/78784280/145406927-b24258c0-04cc-4c60-99fb-eeafa61f566d.PNG" width="800">

### The Pi sends data to the mbed over a wifi ESP8266 module (used in Lab 2). A server was established for their connection. In this case at address http://192.168.1.10/ 
<img src="https://user-images.githubusercontent.com/78784280/145407604-073c9c47-6015-49ab-a1c0-314970d15053.png" width="500">

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Table of Commands
The number of fingers held up by the user will determine the robot’s movement.

| Number of fingers held up  | Robot movement |
| ------------- | ------------- |
| 1  | Forward   |
| 2  | Reverse   |
| 3  | Right Turn|
| 4  | Left Turn |

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Instructions
After obtaining the hardware, follow the instructions that came with each part to setup the environment.

- Raspberry Pi 4
  - https://www.raspberrypi.com/documentation/computers/getting-started.html

- Pi camera
  - *insert link Gary?*

- OpenCV tutorial for hand-gesture detection
  - *insert link Gary*

- Hardware setup
  - Build the robot and setup the Pi and mbed connections following instructions in [Hardware Setups](README.md#hardware-setups)

- Running the code
  - The code to run the mbed can be found here: *insert link to mbed repo*
  - Pi? *how did you guys run the Pi from terminal? what code? do you have to download the code from somewhere and store them somewhere?*

# Demo Video

insert link here

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Future Improvements
- Wider range of robot motions 
- Controllable speed
- Detection of gestures beyond number of fingers
- Secondary camera to the mobile robot for live video

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

