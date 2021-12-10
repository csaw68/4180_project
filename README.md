# Hand Gesture Controlled Robot through OpenCV and an IoT Webserver "CVcar"
ECE 4180 Final Project (Fall 2021 - Section A)

<img src="https://user-images.githubusercontent.com/78784280/145456514-06a19176-1532-46f3-b22f-5fb9e83ddda6.jpeg" width="850">

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
- [Summary Video](README.md#summary-video)
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

## Pin Connection of the Pi
<img src="https://user-images.githubusercontent.com/78784280/145406918-eed09443-98ee-4211-9d10-eaa107adf42a.PNG" width="500">

## Pin Connection of the mbed
<img src="https://user-images.githubusercontent.com/78784280/145406927-b24258c0-04cc-4c60-99fb-eeafa61f566d.PNG" width="800">

### The Pi sends data to the mbed over a wifi ESP8266 module (used in Lab 2). A server was established for their connection. In this case at address http://192.168.1.10/ 
<img src="https://user-images.githubusercontent.com/78784280/145407604-073c9c47-6015-49ab-a1c0-314970d15053.png" width="500">

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Table of Commands
The number of fingers held up by the user will determine the robot’s movement.

| Number of fingers held up  | Robot movement |
| ------------- | ------------- |
| 0  | Hand not Detected - Alerts Users that their hand is not visible  |
| 1  | Forward   |
| 2  | Reverse   |
| 3  | Right Turn|
| 4  | Left Turn |
| 5  | Hand Detected - Alerts Users that their hand is visible and gestures will be tracked |

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Instructions
After obtaining the hardware, follow the instructions that came with each part to setup the environment.

- Raspberry Pi 4
  - https://www.raspberrypi.com/documentation/computers/getting-started.html

- Pi Camera
  - https://projects.raspberrypi.org/en/projects/getting-started-with-picamera

- OpenCV tutorial for hand-gesture detection
  - https://google.github.io/mediapipe/solutions/hands.html

- Hardware setup
  - Build the robot and setup the Pi and mbed connections following instructions in [Hardware Setups](README.md#hardware-setups)

- Running the code
  - mbed LPC1768
    - Compile the *Project_Wifi_Config* program into the mbed to ensure the ESP8266 is connected to the wifi network. **Link to repo**: https://os.mbed.com/users/fyousuf6/code/ECE4180_WirelessGestureControlCar_CVcar_/
    - Compile the *Project_Wifi_Server* program into the mbed. This step initializes the server that connects the Pi and mbed and allows the mbed to receive messages from the Pi. **Link to repo**: https://os.mbed.com/users/fyousuf6/code/ECE4180-WirelessGestureControlCar_CVcar_/rev/ce3305cf50b4/
  - Raspberry Pi 4
    - Download the *Handtracking* files to a directory and open terminal in that directory.
    - Run the hand gesture detection program ```python3 handtracker_to_Server.py```
  

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Summary Video

https://www.youtube.com/watch?v=mAgygFNm7wE

The video above summarizes the basic functionality of the 3 programs needed to control the car:
1. **handtracker_to_Server.py**
  - located in Handtracking folder on Github, must be run in IDE, in our case, we use Thonny
  - uses OpenCV to read hand gestures
  - relies on MediaPipe’s handmodule, which sections the hand into 20 distinct points
  - the main function handles the OpenCV/Computer Vision component of project
  - draws the camera window, tracks current gesture, then sends the number of finger’s held up to the MBED through the send_command() function.
2. **Project_Wifi_Config**
  - located in both MBED repo and Github
  - download the program to the MBED to ensure the ESP8266 is connected to your wifi network
  - terminal will display the IP address of the server (change the address in handetracker_to_Server.py accordingly)
  - the SSID and password of the network is saved to the ESP8266, may need to be rerun if the wifi disconnects
3. **Project_Wifi_Server**
  - located in both MBED repo and Github
  - initializes server, so it is ready to interpret messages from the Pi into motion


[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Demo Video

Short demo video of the robot's operations: https://www.youtube.com/watch?v=9tCQLGX4CgQ&feature=emb_logo

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)

# Future Improvements
- Include a wider range of robot motions 
- Be able to control speed with gestures
- Detection of gestures beyond number of fingers
- Add a secondary camera to the mobile robot for live video as it moves
- Add more detail to the server webpage, such as what command is currently being executed

[back to top](README.md#hand-gesture-controlled-robot-through-opencv-and-an-iot-webserver)


