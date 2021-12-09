## The web page should explain the project idea, provide instructions, code, and hardware setups 
# Hand Gesture Controlled Robot through OpenCV and an IoT Webserver
ECE 4180 Final Project 

insert image of robot - look more legit

# Authors
Feng Yunchu, Faiza Yousuf, Harry Nguyen, Christine Saw

# Overview
This project aims to create a hand gesture-controlled car that can recognize hand commands to move perform four motions of the robot. It uses a Pi camera to capture hand gestures, a Raspberry Pi 4 to interface with the Pi camera and translate detected hand gestures into commands that are sent to a server run by an MBED (using a ESP8266 module).

<img src="https://user-images.githubusercontent.com/78784280/145406626-4b1c1e76-71f7-47f4-ae24-0832096a899d.png" width="800">

# Parts List
Hardware:
- Raspberry Pi 4
- Pi Camera
- DC motors 
- Dual H-bridge breakout board 
- LED lights
- Power supply with stable amp (4AA battery pack and power bank)
- ESP8266

Software:
- Python 3
- OpenCV
- Thonny - compiler seen in demo
- MBED online compiler

# Hardware Setups

## Pin connection of the Pi
<img src="https://user-images.githubusercontent.com/78784280/145406918-eed09443-98ee-4211-9d10-eaa107adf42a.PNG" width="800">

## Pin connection of the mbed
<img src="https://user-images.githubusercontent.com/78784280/145406927-b24258c0-04cc-4c60-99fb-eeafa61f566d.PNG" width="800">

### ** unsure on elaboration ** The mbed and Pi exchange information over a wifi module (used in Lab 2). A server was established for their connection. 
<img src="https://user-images.githubusercontent.com/78784280/145407604-073c9c47-6015-49ab-a1c0-314970d15053.png" width="500">

# Table of Commands
The number of fingers held up by the user will determine the robot’s movement.

| Number of fingers held up  | Robot movement |
| ------------- | ------------- |
| 1  | Forward   |
| 2  | Reverse   |
| 3  | Right Turn|
| 4  | Left Turn |

# Demo Video

insert link here

# Future Improvements

